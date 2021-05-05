<template>
  <div class="wrapper">
    <parallax class="page-header header-filter" style="background-image: url('/img/vue-mk-header.6d5b72b7.jpg'); transform: translate3d(0px, 0px, 0px);">
      <div class="md-layout">
        <div class="md-layout-item">
          <div class="image-wrapper">
            <div class="brand">
              <h1>Eduvision</h1>
              
              <h3 style="height:80px;"><vue-typer :text="typerText" style="color:white;"></vue-typer></h3>
              <div style="width:100%; margin-top:35px;">
                <md-button class="md-warning md-round" style="font-size: x-large; margin-left:25px; margin-right:25px;" 
                @click="goToCourses">Courses</md-button>
                <md-button class="md-primary md-round" style="font-size: x-large; margin-right:25px; margin-left:25px;"
                @click="goToGetInTouch">Get In Touch</md-button>
              </div>
                
            </div>
          </div>
        </div>
      </div>
    </parallax>
    <div class="main main-raised">
      <div class="section section-basic" style="padding-top:0px; padding-bottom:30px;">
        <div class="md-layout">
          <div class="md-layout-item" style="width:100%; text-align:center;">
            <h3 class="heading-3">Small group coaching</h3>
            <badge type="warning" style="font-size:xx-large;margin-top:10px;">Face-to-face</badge>
            <badge type="primary"  style="font-size:xx-large;margin-top:10px;">Online</badge>
          </div>
        </div>
      </div>
    </div>
    
    <div class="main_ main-raised_" id="Courses">
      <h2 class="heading-2">Popular Courses</h2>
      <div class="section section-basic" style="padding-top:0px;">
      <div class="container">
          <div class="md-layout">
            <div v-for="course in courses" v-bind:key="course.id" class="md-layout-item">
              <login-card header-color="orange">
                <h4 slot="title" class="card-title">{{course.title}}</h4>
                <div slot="description">
                  <div class="card-meta-info">
                    <div style="display:inline; margin-right:30px;"><strong>Enrollment:</strong></div>
                    <span v-bind:style="getOpenCloseWeight(course)">{{course.enrollmentOpen?'Open':'Closed'}}</span>
                  </div>
                  <div class="card-meta-info">
                    <div style="display:inline; margin-right:30px;"><strong>For Year:</strong></div>
                    <span>{{course.courseFor}}</span>
                  </div>
                  <p class="card-description">{{course.description}}</p>
                </div>
                
                
                <md-button slot="footer" class="md-simple md-success">
                  {{course.primaryAction.label}}
                </md-button>
                <md-button slot="footer" class="md-simple md-success">
                  {{course.secondaryAction.label}}
                </md-button>
              </login-card>
            </div>
            
            
          </div>
        </div>
        </div>
      
    </div>
    <!-- All Courses -->
    <div class="main main-raised" style="margin-bottom:0px;">
      <div class="section section-basic" style="padding-top:0px; padding-bottom:30px;">
        <div class="md-layout">
          <div class="md-layout-item" style="width:100%; text-align:center;">
            <h3 class="heading-3">Looking for course? Explore
              <md-button class="md-warning md-round" style="margin-top:-5px; margin-left:25px; margin-right:25px;" 
                @click="goToCourses">All Courses</md-button>
            </h3>
          </div>
        </div>
      </div>
    </div>
    <!-- testinomial carousal https://www.npmjs.com/package/vue-carousel -->
    <div class="main_ main-raised_">
      <h2 class="heading-2">Hear from parents just like you</h2>
      <div class="section section-basic" style="padding-top:0px;">
      <div class="container">
            
            <carousel :per-page="1"
            :autoplay="true" 
            :touchDrag="true" 
            :loop="true" 
            :adjustableHeight="true"
            :mouse-drag="true">
            <slide v-for="(s, index) in getTestimonialSlides()" v-bind:key="index">
              
              <div class="md-layout">
                <div v-for="t in s" v-bind:key="t.id" class="md-layout-item">
                  <login-card header-color="orange">
                    <h4 slot="title" class="card-title">{{t.name}}<br>{{t.ref}}</h4>
                    <div slot="description">
                      
                      <p class="card-description">{{t.msg}}</p>
                    </div>
                  </login-card>
                </div>
              </div>
            </slide>
            </carousel>
            
          </div>
        </div>
    </div>
    <!-- out Team -->
    <div class="main main-raised" style="background:radial-gradient(circle, #046eb8, #fb8c00, #ff9800, green);" id="team">
      <div class="section section-basic" style="padding-top:0px; padding-bottom:30px;">
        <div class="md-layout_">
          <div class="md-layout-item_" style="width:100%; text-align:center;">
            <h2>Our Specialized Team</h2>
          </div>
          <div class="md-layout" style="text-align: center;">
              <div class="md-layout-item md-size-20 md-xsmall-size-100 ml-auto"
                  :class="{ 'text-center': responsive }">
                <h4>FirstName LastName</h4>
                <a href="#/profile"><img
                  src="/img/avatar.cc93a967.jpg"
                  alt="Thumbnail Image"
                  class="img-raised rounded-circle"
                  :class="{ 'responsive-image': responsive }"
                /></a>
              </div>
              <div class="md-layout-item md-size-20 md-xsmall-size-100 ml-auto"
                  :class="{ 'text-center': responsive }">
                <h4>FirstName LastName</h4>
                <a href="#/profile"><img
                  src="/img/avatar.cc93a967.jpg"
                  alt="Thumbnail Image"
                  class="img-raised rounded-circle"
                  :class="{ 'responsive-image': responsive }"
                /></a>
              </div>
              <div class="md-layout-item md-size-20 md-xsmall-size-100 ml-auto"
                  :class="{ 'text-center': responsive }">
                <h4>FirstName LastName</h4>
                <a href="#/profile"><img
                  src="/img/avatar.cc93a967.jpg"
                  alt="Thumbnail Image"
                  class="img-raised rounded-circle"
                  :class="{ 'responsive-image': responsive }"
                /></a>
              </div>
              <div class="md-layout-item md-size-20 md-xsmall-size-100 ml-auto"
                  :class="{ 'text-center': responsive }">
                <h4>FirstName LastName</h4>
                <a href="#/profile"><img
                  src="/img/avatar.cc93a967.jpg"
                  alt="Thumbnail Image"
                  class="img-raised rounded-circle"
                  :class="{ 'responsive-image': responsive }"
                /></a>
                </div>
          </div>
        </div>
      </div>
    </div>
    <!-- contact us -->
    <div class="main_ main-raised_" id="contact_us">
      <h2 class="heading-2">Contact Us</h2>
      <div class="section section-basic" style="padding-top:0px;">
        <div class="container" style="background-color:#ff9800;">
          <div class="md-layout">
          <div class="md-layout-item" style="width:100%; text-align:left; justtify-content:start;">
            <h3 class="heading-2">Shape the future of your child.</h3>
            <h4><strong>Phone:</strong>&nbsp;&nbsp;&nbsp;<a href="tel:042336699642">+61 042336699642</a></h4>
            <h4><strong>Email:</strong>&nbsp;&nbsp;&nbsp;<a href="mailto:info@eduvision.com.au">info@eduvision.com.au</a></h4>
            <h4><strong>Facebook:</strong>&nbsp;&nbsp;&nbsp;<a href="https://www.facebook.com/eduvision.au" target="_blank">EduVision Au</a></h4>
            <h4><strong>WeChat Customer Service:</strong></h4>
            <img src="https://eduvision.com.au/Files/2020/58F725A604D61FBE549BBA57A84491EF3CECFDC9CDD4AEA77F68948366E325A8.jpg" width="200px;" height="200px"/>
          </div>  
          <div class="md-layout-item" style="width:100%; text-align:center;">
            <h2>Or we'll reach out to you</h2>
            <div style="background-color:#ffffff; padding:10px;">
              <md-field class="md-form-group" slot="inputs">
                <md-icon style="color:#ABCDEF;">face</md-icon>
                <label>Full Name...</label>
                <md-input v-model="firstname"></md-input>
              </md-field>
              <md-field class="md-form-group" slot="inputs">
                <md-icon style="color:#ABCDEF;">email</md-icon>
                <label>Email...</label>
                <md-input v-model="email" type="email"></md-input>
              </md-field>
              <md-field class="md-form-group" slot="inputs">
                <md-icon style="color:#ABCDEF;">phone</md-icon>
                <label>Phone...</label>
                <md-input v-model="email" type="email"></md-input>
              </md-field>
              <md-field class="md-form-group" slot="inputs">
                <md-icon style="color:#ABCDEF;">message</md-icon>
                <label>How we can help?...</label>
                <md-textarea v-model="password"></md-textarea>
              </md-field>
              <md-button class="md-primary md-round" style="font-size: large; margin-right:25px; margin-left:25px;"
                @click="clickContactMe">Contact Me</md-button>
            </div>
          </div>  
          <div style="width:100%; padding-left:15px; padding-right:15px; padding-bottom:15px;">
            <h4><strong>Address:</strong>
            <a href="https://maps.google.com/?q=16-18 Cambridge Street, Epping NSW 2121" target="_blank">
            &nbsp;&nbsp;&nbsp;
            Suite 402, 16-18 Cambridge Street, Epping NSW 2121</a>
            <strong style="display:block; color:black;">(It is around 3 minutes walk from the Epping Station.)</strong></h4>
            <img src="https://eduvision.com.au/Files/2020/EduVision-Location.jpg" width="100%" height="auto"/>
            <strong style="display:block; color:black; margin-top:15px;">Please be aware that from Langston Pl, you cannot turn left onto Cambridge St, and cannot turn right onto Beecroft rd.
            </strong>
          </div>
        </div>
      </div>
      </div>
    </div>
    <!-- FAQ -->
    <div class="main main-raised" id="faq">
      <div class="section section-basic" style="padding-top:0px; padding-bottom:30px;">
        <div class="md-layout_">
          <div class="md-layout-item" style="width:100%; text-align:center;">
            <h2 class="heading-3">Frequently Asked Questions.</h2>

            <VueFaqAccordion 
              :items="myItems"
            />
          </div>
        </div>
      </div>
    </div>
    <!-- To delete -->
  <!-- <div class="main main-raised" style="margin-top:100px;">
    <div class="section section-basic">
      <div class="container">
        <div class="title">
          <h2>Basic Elements</h2>
        </div>
        <basic-elements></basic-elements>
      </div>
    </div>
    <div class="section section-navbars">
      <div class="container">
        <small-navigation></small-navigation>
      </div>
      <navigation></navigation>
    </div>
    <div class="section section-tabs">
      <div class="container">
        <tabs></tabs>
      </div>
    </div>
    <div class="section section-white">
      <div class="container">
        <nav-pills></nav-pills>
      </div>
    </div>
    <div class="section section-notifications">
      <div class="container">
        <div class="title">
          <h3>Notifications</h3>
        </div>
      </div>
      <notifications></notifications>
    </div>
    <div class="section">
      <div class="container">
        <typography-images></typography-images>
      </div>
    </div>
    <div class="section section-javascript">
      <div class="container">
        <javascript-components></javascript-components>
      </div>
    </div>
    <div class="section">
      <div class="container text-center">
        <div class="md-layout">
          <div
            class="md-layout-item md-size-66 md-xsmall-size-100 ml-auto mr-auto text-center"
          >
            <h2>Completed with examples</h2>
            <h4>
              The kit comes with three pre-built pages to help you get started
              faster. You can change the text and images and you're good to
              go. More importantly, looking at them will give you a picture of
              what you can built with this powerful kit.
            </h4>
          </div>
        </div>
      </div>
    </div>
    <div class="section section-signup page-header" :style="signupImage">
      <div class="container">
        <div class="md-layout">
          <div
            class="md-layout-item md-size-33 md-medium-size-40 md-small-size-50 md-xsmall-size-70 mx-auto text-center"
          >
            <login-card header-color="green">
              <h4 slot="title" class="card-title">Login</h4>
              <md-button
                slot="buttons"
                href="javascript:void(0)"
                class="md-just-icon md-simple md-white"
              >
                <i class="fab fa-facebook-square"></i>
              </md-button>
              <md-button
                slot="buttons"
                href="javascript:void(0)"
                class="md-just-icon md-simple md-white"
              >
                <i class="fab fa-twitter"></i>
              </md-button>
              <md-button
                slot="buttons"
                href="javascript:void(0)"
                class="md-just-icon md-simple md-white"
              >
                <i class="fab fa-google-plus-g"></i>
              </md-button>
              <p slot="description" class="description">Or Be Classical</p>
              <md-field class="md-form-group" slot="inputs">
                <md-icon>face</md-icon>
                <label>First Name...</label>
                <md-input v-model="firstname"></md-input>
              </md-field>
              <md-field class="md-form-group" slot="inputs">
                <md-icon>email</md-icon>
                <label>Email...</label>
                <md-input v-model="email" type="email"></md-input>
              </md-field>
              <md-field class="md-form-group" slot="inputs">
                <md-icon>lock_outline</md-icon>
                <label>Password...</label>
                <md-input v-model="password"></md-input>
              </md-field>
              <md-button slot="footer" class="md-simple md-success md-lg">
                Get Started
              </md-button>
            </login-card>
          </div>
        </div>
      </div>
    </div>
    <div class="md-layout">
      <div class="md-layout-item text-center">
        <md-button href="#/login" class="md-simple md-success md-lg"
          >View Login Page</md-button
        >
      </div>
    </div>
    <div class="section section-examples">
      <div class="container-fluid text-center">
        <div class="md-layout">
          <div class="md-layout-item">
            <a href="#/landing" target="_blank">
              <img
                :src="landing"
                alt="Rounded Image"
                class="img-raised rounded img-fluid"
              />
            </a>
            <md-button href="#/landing" class="md-simple md-success md-lg"
              >View Landing Page</md-button
            >
          </div>
          <div class="md-layout-item">
            <a href="#/profile" target="_blank">
              <img
                :src="profile"
                alt="Rounded Image"
                class="img-raised rounded img-fluid"
              />
            </a>
            <md-button href="#/profile" class="md-simple md-success md-lg"
              >View Profile Page</md-button
            >
          </div>
        </div>
      </div>
    </div>
    <div class="section section-download" id="downloadSection">
      <div class="container">
        <div class="md-layout text-center">
          <div class="md-layout-item md-size-66 md-small-size-100 mx-auto">
            <h2>Do you love this UI Kit?</h2>
            <h4>
              Cause if you do, it can be yours for FREE. Hit the buttons below
              to navigate to our website where you can find the kit. Our
              friends from
              <a
                href="https://themeisle.com/?utm_campaign=mkfree-hestia&amp;utm_source=creativetim&amp;utm_medium=website"
                target="_blank"
                >ThemeIsle</a
              >
              created a Wordpress Theme which can be also downloaded for free.
              Start a new project or give an old Bootstrap project a new look!
            </h4>
          </div>
          <div class="md-layout-item md-size-50 md-small-size-100 mx-auto">
            <md-button
              href="https://www.creative-tim.com/product/material-kit"
              target="_blank"
              class="md-success md-lg"
              ><i class="fab fa-html5"></i> Free HTML Download</md-button
            >
            <md-button
              href="https://themeisle.com/themes/hestia/?utm_campaign=mkfree-hestia&amp;utm_source=creativetim&amp;utm_medium=website"
              class="md-success md-lg"
              target="_blank"
              ><i class="fab fa-wordpress"></i> Wordpress Theme</md-button
            >
          </div>
        </div>
        <br /><br />

        <div class="md-layout text-center">
          <div class="md-layout-item md-size-66 md-small-size-100 mx-auto">
            <h2>Want more?</h2>
            <h4>
              We've just launched
              <a
                href="https://www.creative-tim.com/product/vue-material-dashboard-pro?ref=utp-mk-demos"
                target="_blank"
                >Vue Material Dashboard PRO</a
              >
              and
              <a
                href="https://www.creative-tim.com/product/vue-material-kit-pro?ref=utp-vmk-demos"
                target="_blank"
                >Vue Material Kit PRO</a
              >. Every product has a huge number of components, sections and
              example pages. Start Your Development With A Badass Bootstrap UI
              Kit inspired by Material Design.
            </h4>
          </div>
          <div class="md-layout-item md-size-50 md-small-size-100 mx-auto">
            <div class="btn-container">
              <md-button
                href="https://www.creative-tim.com/product/vue-material-kit-pro?ref=utp-vmk-demos"
                class="md-button md-success md-lg md-upgrade"
                target="_blank"
                ><md-icon>unarchive</md-icon>Vue Material Kit PRO</md-button
              >
              <md-button
                href="https://www.creative-tim.com/product/vue-material-dashboard-pro?ref=utp-vmd-demos"
                class="md-button md-success md-lg md-upgrade"
                target="_blank"
                ><md-icon>unarchive</md-icon>Vue Material Dashboard
                PRO</md-button
              >
            </div>
          </div>
        </div>

        <div class="sharing-area text-center">
          <div class="md-layout">
            <div class="md-layout-item">
              <h3>Thank you for supporting us!</h3>
            </div>
          </div>

          <md-button class="md-twitter"
            ><i class="fab fa-twitter"></i>Tweet</md-button
          >
          <md-button class="md-facebook"
            ><i class="fab fa-facebook-square"></i> Share</md-button
          >
          <md-button class="md-google"
            ><i class="fab fa-google-plus"></i> Share</md-button
          >
          <md-button class="md-github"
            ><i class="fab fa-github"></i> Star</md-button
          >
        </div>
      </div>
    </div>
  </div> -->
    </div>
</template>

<script>
// import BasicElements from "./components/BasicElementsSection";
// import Navigation from "./components/NavigationSection";
// import SmallNavigation from "./components/SmallNavigationSection";
// import Tabs from "./components/TabsSection";
// import NavPills from "./components/NavPillsSection";
// import Notifications from "./components/NotificationsSection";
// import TypographyImages from "./components/TypographyImagesSection";
// import JavascriptComponents from "./components/JavascriptComponentsSection";
import { LoginCard } from "@/components";
import { VueTyper } from 'vue-typer';
import { Badge } from "@/components";
import VueCarousel from 'vue-carousel';
import { Carousel, Slide } from 'vue-carousel';
import Vue from 'vue';
import VueFaqAccordion from 'vue-faq-accordion'
 
Vue.use(VueCarousel);

export default {
  components: {
    // BasicElements,
    // Navigation,
    // SmallNavigation,
    // Tabs,
    // NavPills,
    // Notifications,
    // TypographyImages,
    // JavascriptComponents,
    LoginCard,
    VueTyper,
    Badge,
    Carousel,
    Slide,
    VueFaqAccordion
  },
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/vue-mk-header.jpg")
    },
    leaf4: {
      type: String,
      default: require("@/assets/img/leaf4.png")
    },
    leaf3: {
      type: String,
      default: require("@/assets/img/leaf3.png")
    },
    leaf2: {
      type: String,
      default: require("@/assets/img/leaf2.png")
    },
    leaf1: {
      type: String,
      default: require("@/assets/img/leaf1.png")
    },
    signup: {
      type: String,
      default: require("@/assets/img/city.jpg")
    },
    landing: {
      type: String,
      default: require("@/assets/img/landing.jpg")
    },
    profile: {
      type: String,
      default: require("@/assets/img/profile.jpg")
    }
  },
  data() {
    return {
      responsive: true,
      firstname: null,
      email: null,
      password: null,
      leafShow: false,
      typerText: ['An Investment in knowledge pays the best interest', 'Primary and High School','Personalised and research-based coaching taught by highly qualified teachers'],
      courses: [
        {
          id: '001',
          title: 'English',
          description: 'Some details',
          enrollmentOpen: 'true',
          courseFor: 'Year 3 to 12',
          primaryAction: {
            label: 'GET STARTED',
            link: '#'
          },
          secondaryAction: {
            label: 'KNOW MORE',
            link: '#'
          }
        },
        {
          id: '002',
          title: 'Maths',
          description: 'Math Couese Some details; Need text to describe this course. text of 3 lines at max.',
          enrollmentOpen: false,
          courseFor: 'Year 3 to 12',
          primaryAction: {
            label: 'GET STARTED',
            link: '#'
          },
          secondaryAction: {
            label: 'KNOW MORE',
            link: '#'
          }
        },
        {
          id: '003',
          title: 'Thinking Skills',
          description: 'Thinking Skills Some details; Need text to describe this course. text of 3 lines at max.',
          enrollmentOpen: false,
          courseFor: 'Year 3 to 12',
          primaryAction: {
            label: 'GET STARTED',
            link: '#'
          },
          secondaryAction: {
            label: 'KNOW MORE',
            link: '#'
          }
        },
        {
          id: '004',
          title: 'Debating',
          description: 'Debating Some details; Need text to describe this course. text of 3 lines at max.',
          enrollmentOpen: 'true',
          courseFor: 'Year 3 to 12',
          primaryAction: {
            label: 'GET STARTED',
            link: '#'
          },
          secondaryAction: {
            label: 'KNOW MORE',
            link: '#'
          }
        },
        {
          id: '005',
          title: 'Selective Trial Tests',
          description: 'Selective Trial Tests is a special program for selective studentsSome special program for selective studentsSome special program for selective studentsSome details',
          enrollmentOpen: 'true',
          courseFor: 'Year 4 to 6',
          primaryAction: {
            label: 'GET STARTED',
            link: '#'
          },
          secondaryAction: {
            label: 'KNOW MORE',
            link: '#'
          }
        },
        {
          id: '006',
          title: 'OC Trial Tests',
          description: 'OC Trial Tests is a special program for details; Need text to describe this course. text of 3 lines at max.',
          enrollmentOpen: 'true',
          courseFor: 'Year 3 to 4',
          primaryAction: {
            label: 'GET STARTED',
            link: '#'
          },
          secondaryAction: {
            label: 'KNOW MORE',
            link: '#'
          }
        }
      ],
      testimonials: [
        {
          id: '001',
          name: 'Nagendra Shukla',
          ref: 'Father of Sharanya, Year 6',
          msg: 'Something good about Eduvision; but it may be too long too, So we need to restrict its length at some point to keep all cards consisent. For now assuming 150 px of content and if more then there should be scrollbar within content.'
        },
        {
          id: '002',
          name: 'Nagendra Shukla',
          ref: 'Father of Sharanya, Year 6',
          msg: 'Something good about Eduvision; but it may be too long too, So we need to restrict its length at some point to keep all cards consisent. For now assuming 150 px of content and if more then there should be scrollbar within content.'
        },
        {
          id: '003',
          name: 'Nagendra Shukla',
          ref: 'Father of Sanvi, Year 4',
          msg: 'Something good about Eduvision; but it may be too long too, So we need to restrict its length at some point to keep all cards consisent. For now assuming 150 px of content and if more then there should be scrollbar within content.'
        },
        {
          id: '004',
          name: 'Nagendra Shukla',
          ref: 'Father of Shashwat, Year 1',
          msg: '4th Item.Something good about Eduvision; but it may be too long too, So we need to restrict its length at some point to keep all cards consisent. For now assuming 150 px of content and if more then there should be scrollbar within content.'
        },
        {
          id: '005',
          name: 'Sandhya Shukla',
          ref: 'Mother of Sharanya, Year 6',
          msg: '5th Item. Something good about Eduvision; but it may be too long too, So we need to restrict its length at some point to keep all cards consisent. For now assuming 150 px of content and if more then there should be scrollbar within content.'
        },
        {
          id: '006',
          name: 'Sandhya Shukla',
          ref: 'Mother of Sanvi, Year 4',
          msg: '6th item. Something good about Eduvision; but it may be too long too, So we need to restrict its length at some point to keep all cards consisent. For now assuming 150 px of content and if more then there should be scrollbar within content.'
        },
        {
          id: '007',
          name: 'Sandhya Shukla',
          ref: 'Mother of Sanvi, Year 4',
          msg: '7th item. Something good about Eduvision; but it may be too long too, So we need to restrict its length at some point to keep all cards consisent. For now assuming 150 px of content and if more then there should be scrollbar within content.'
        }
      ],
      myItems: [
          {
            title: 'What is your course outline?',
            value: 'In keeping with our vision, EduVision hire only the highest calibre teachers in their field. Our courses are carefully designed to support students through various levels of their schooling.  We also help prepare students across a variety of exams including OC, Selective, Scholarship, G&T Classes and Maths Competitions.',
            category: 'FAQ'
          },
          {
            title: 'How do your online classes work?',
            value: 'We use Zoom for our online classroom featuring interactive chat, screen share and discussions. We also have a Google Classroom for uploading lesson booklets, homework and the submission of writing homework. Detailed feedback is provided via Google Classroom.',
            category: 'FAQ'
          },
          {
            title: 'Can you support my child in their Scholarship application?',
            value: 'Yes, we have experience supporting our students in scholarship applications. This year, our students have received over 49 interview offers.',
            category: 'FAQ'
          },
          {
            title: 'What are your class sizes?',
            value: `Our online classes are around 12 students.<br/>Our face-to-face classes are around 15 students.`,
            category: 'FAQ'
          },
          {
            title: 'How do I pay for my child’s classes?',
            value: `Please make direct deposit into below bank account. 
            Please use your <strong>STUDENT ID</strong> and <strong>CLASS ID </strong> as the Reference:<br>
            Account name: <strong>EduVision Pty Ltd.</strong><br>
BSB: <strong>032282</strong><br>
Account number: <strong>412607</strong><br>`,
            category: 'FAQ'
          },
          {
            title: 'Where are you located?',
            value: `<h4><strong>Address:</strong>
            <a href="https://maps.google.com/?q=16-18 Cambridge Street, Epping NSW 2121" target="_blank">
            &nbsp;&nbsp;&nbsp;
            Suite 402, 16-18 Cambridge Street, Epping NSW 2121</a>
            <strong style="display:block; color:black;">(It is around 3 minutes walk from the Epping Station.)</strong></h4>`,
            category: 'FAQ'
          },
          
        ]
    };
  },
  methods: {
    goToCourses() {
      alert('This should take to courses');
    },
    goToGetInTouch() {
      alert('This should take to goToGetInTouch');
    },
    clickContactMe() {
      alert('Thanks for sharing your details; our team will contact you.');
    },
    
    getOpenCloseWeight(course) {
      return {fontWeight: course.enrollmentOpen?'bold':'normal'};
    },
    getTestimonialSlides() {
      let slides = [];
      for(let i = 0; i < this.testimonials.length; i++) {
        let count = parseInt(i / 3);
        if(!slides[count]) {
          // alert('....'+slides[count]+' :: '+i+' :: '+count);
          slides[count] = new Array();
        }
        slides[count].push(this.testimonials[i]);
        // alert('..aa..'+slides[count]+' :: '+i);
      }
      return slides;
    },
    leafActive() {
      if (window.innerWidth < 768) {
        this.leafShow = false;
      } else {
        this.leafShow = true;
      }
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss">
.intro-btn {
  background-color: #ABCDEF;
  font-weight: bold;
}

.md-card .md-card-header {
  margin-top: 0px !Important;
}
.md-card .md-card-content {
  padding: 5px !important;
}
.heading-2 {
  width:100%; text-align:center; color:#ffffff; font-weight:bolder; 
}
.heading-3 {
  color:#000000; font-weight:bolder; 
}
.card-meta-info {
      display: flex;
    /* justify-items: right; */
    justify-content: space-around;
}
.card-description {
    color: black !important;
    text-align: justify !important;
    max-height: 70px;
    overflow: auto;
    text-overflow: ellipsis;
    height: 70px;
  
  }
@media only screen and (max-width: 600px) {
  .card-description {
    color: black !important;
    text-align: justify !important;
    max-height: 120px;
    overflow: auto;
    text-overflow: ellipsis;
    height: 120px;
  
  }
}
.md-card-login .md-card-actions {
  justify-content: space-between !important;
}
.md-layout-item {
  margin-top: 20px !Important;
}
.vue-typer .custom.char.typed {
  color: #ffffff;
}
.section-download {
  .md-button + .md-button {
    margin-left: 5px;
  }
}

@media all and (min-width: 991px) {
  .btn-container {
    display: flex;
  }
}
</style>
