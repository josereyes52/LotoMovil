<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-dark">
              <div class="container">
                <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarsExample07" aria-controls="navbarsExample07" aria-expanded="false" aria-label="Toggle navigation">
                  <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarsExample07">
                  <ul class="navbar-nav mr-auto">
                    <li class="nav-item active">
                      <a class="nav-link" v-bind:href="links.home">Home</a>
                    </li>
                    <li class="nav-item dropdown">
                      <a class="nav-link dropdown-toggle" href="#" id="dropdown07" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Other</a>
                      <div class="dropdown-menu" aria-labelledby="dropdown07">
                            <a v-for="index, link of links.other" v-bind:key="link" class="dropdown-item" v-bind:href="link">{{ index }}</a>
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
            </nav>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            links:{
                home: '/',
                other: {
                    Result: 'Result.html',
                    Terms: 'Terms-of-Use.html',
                    Privacy: 'Privacy-Policy.html'
                }
            }
        }
    },
    methods: {
        //
    }
}

</script>