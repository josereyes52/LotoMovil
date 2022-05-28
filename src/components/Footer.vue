<template>
    <!-- Footer -->
    <footer class="text-center text-lg-start">
        <!-- Section: Social media -->
        <section class="d-flex container justify-content-center justify-content-lg-between p-4 border-bottom">
            <!-- Left -->
            <div class="me-5 d-none d-lg-block">
                <span>{{socialMedia.title}}</span>
            </div>
            <!-- Left -->

            <!-- Right -->
            <div>
                <a v-bind:href="social.link" class="me-4 text-reset" :aria-label="social.name" v-for="(social,index) of socialMedia.icon" v-bind:key="index">
                    <i v-bind:class="social.icon"></i>
                </a>
            </div>
            <!-- Right -->
        </section>
        <!-- Section: Social media -->

        <!-- Copyright -->
        <div class="text-center p-4" style="background-color: rgba(0, 0, 0, 0.05);">
            {{copyright}}

            <div class="copyright-links">
                <a href="{{copyrightLinks.Terms}}" aria-label="Terms of Use" >Terms of Use</a> / 
                <a href="{{copyrightLinks.Privacy}}" aria-label="Privacy Policy" >Privacy Policy</a>
            </div>
        </div>
        <!-- Copyright -->
    </footer>
    <!-- Footer -->
</template>

<script>
export default {
    name: 'Footer',
    data() {
        return {
            copyrightLinks:{
                Terms: 'Terms-of-Use.html',
                Privacy: 'Privacy-Policy.html'
            },
            copyright: '© 2020 All Rights Reserved by ESI Lotto page.',
            socialMedia: {
                title: 'Get connected with us on social networks:',
                icon: [
                    {
                        name: 'facebook',
                        icon: 'fab fa-facebook-f',
                        link: 'https://www.facebook.com/ESILotto/'
                    },
                    {
                        name: 'twitter',
                        icon: 'fab fa-twitter',
                        link: 'https://twitter.com/ESILotto'
                    },
                    {
                        name: 'google',
                        icon: 'fab fa-google',
                        link: 'https://www.google.com/'
                    },
                    {
                        name: 'instagram',
                        icon: 'fab fa-instagram',
                        link: 'https://www.instagram.com/esilotto/'
                    },
                    {
                        name: 'linkedin',
                        icon: 'fab fa-linkedin',
                        link: 'https://www.linkedin.com/company/esilotto/'
                    }
                ]
            }
        }
    },
    methods: {
        //
    }
}
</script>
