<template>
<div class="column is-12 box">
  <div class="about">
    <h1 > Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam placerat, turpis vitae tincidunt pharetra, nulla sapien imperdiet odio, eu rhoncus odio lacus vel nisi. Donec diam sapien, luctus ac blandit a, consectetur sed dui. Mauris euismod tempor lacinia. Nulla dignissim convallis vulputate. Quisque ex est, volutpat a egestas consequat, interdum non nulla. Vestibulum non faucibus neque. Donec ac vehicula ante. In nec tincidunt ipsum, at scelerisque dui. Morbi tempus pellentesque libero, id venenatis lectus lobortis sed. Praesent ut diam blandit, porttitor dui pellentesque, elementum massa. Nam rhoncus blandit orci id laoreet. Nullam sagittis libero nec elit dignissim vestibulum. Sed elementum ex at ipsum condimentum aliquam. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.

Mauris eget purus et mauris accumsan rhoncus. Donec vel accumsan mauris. Sed ut ultrices odio, et ullamcorper est. In laoreet sollicitudin lorem at ultrices. Quisque in eros ultricies, tristique eros non, molestie velit. Morbi vel augue nec velit dignissim vulputate. Phasellus congue iaculis nunc, eu ullamcorper metus. Morbi malesuada risus ac euismod consequat.

    </h1>
    <div class="column is-12 box"> FAQ:
      
    <h1>
      1. How can i do ...............?
    </h1>
    <h1> In laoreet sollicitudin lorem at ultrices.
    </h1>
    <h1>How can i do ...............?
    </h1>
    <h1>Donec diam sapien, luctus ac blandit a, consectetur sed dui. Mauris euismod tempor lacinia.
    </h1></div>
     
    
  </div>
     <div class="column is-12 box">
        <h2 class="subtitle">Give us feedback!</h2>

        <p class="has-text-grey mb-4">What you liked about our product?</p>

        <div class="field">
            <div class="control">
                <input type="text" class="input" v-model="place">
            </div>
        </div>

        <p class="has-text-grey mb-4">What you didn't liked about our product?</p>

        <div class="field">
            <div class="control">
                <input type="text" class="input" v-model="place">
            </div>
        </div>

        <p class="has-text-grey mb-4">How can we improve?</p>

        <div class="field">
            <div class="control">
                <input type="text" class="input" v-model="place">
            </div>
        </div>

        <p class="has-text-grey mb-4">What products will you like to see on our store?</p>

        <div class="field">
            <div class="control">
                <input type="text" class="input" v-model="place">
            </div>
        </div>

     </div>
     <div class="column is-12 box">

                <hr>

                <router-link to="/myAccount" class="button is-dark">SEND</router-link>
            </div>
  </div>
</template>
