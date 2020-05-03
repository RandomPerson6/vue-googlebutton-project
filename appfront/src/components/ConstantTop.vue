<template>
  <div class="constanttop">
    <!-- Got rid of b-column because row would not occupy full width, reference site: https://stackoverflow.com/questions/43741988/bootstrap-row-not-occupying-100-width -->
    <b-row class="text-center">
      <b-col xl="3" lg="3">1 of 3</b-col>
      <b-col xl="6" lg="6">
        <b-row>
          <b-col><img src="../assets/logo.png" alt="Library Logo"></b-col>
          <b-col cols="5">
            <b-row class="text-center" align-h="center">
              <b-form inline>
                <b-col cols="8">
                  <label class="sr-only" for="inline-form-input-name">Name</label>
                  <b-input
                    id="inline-form-input-name"
                    placeholder="Search"
                  ></b-input>
                </b-col>
                <b-col><b-button size="md">Submit</b-button></b-col>
              </b-form>
            </b-row>
          </b-col>
          <b-col>
            <ul>
              <li v-for="link in links.link" :key="link.name">
                <a :href="link.url">{{ link.name }}</a>
              </li>
            </ul>
          </b-col>
        </b-row>
      </b-col>
      <b-col xl="3" lg="3">3 of 3</b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: 'ConstantTop',
  data: function() {
    return {
      /* nested arrays thanks to this link reference: https://stackoverflow.com/questions/37534249/nested-arrays-of-objects-and-v-for */
      links: {
        link: [{
          name: 'Home',
          url: '/home/'
        },
        {
          name: 'A to Z Services',
          url: '/atozserives/'
        },
        {
          name: 'Contact Us',
          url: '/contact/'
        },
        {
          name: 'Francais',
          url: '/fr/'
        }
        ]
      }
    };
  },
  props: {
  }
}
</script>

<style scoped>
  * {
    display: inline-block;
  }
  .constanttop {
    background: linear-gradient(to right, #455a64 0%, #ffffff 100%); /* got from: https://www.w3schools.com/colors/colors_gradient.asp */
    width: 100%;
  }
  .container {
    width: 100%
  }
  li {
    list-style-type: none;
    display: block;
  }
  img {
    height:100px;
  }
</style>
