<template>
    <h3>Planet+</h3>

    <span class="header-wrapper">
        <h4 class="header-wrapper-test">
            We transform how data and Knowledge on biodiversity
            is collected, analysed, accessed, and used
        </h4>
    </span>
    <section>
        <table class="table">
      <thead>
        <tr>
          <th scope="col">Id</th>
          <th scope="col">Name</th>
          <th scope="col">Email</th>
          <th scope="col">City</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" v-bind:key="user.id"> 
          <th scope="row">{{user.id}}</th>
          <td>{{user.name}}</td>
          <td>{{user.email}}</td>
          <td>{{user.address.city}}</td>
        </tr>
      </tbody>
    </table> 
    </section>
</template>

<script>
import axios from 'axios';

    export default {
        name: 'MovieListing',
        data() {
            return {
                movie: null,
            }
        },
        created: () => {
            axios
            .get('https://api.spacexdata.com/v3/rockets')
            .then(res => {
                console.log(res.data.map(ele => console.log(ele.flickr_images)));
                this.movie = res.data;
            })
        }
    }
</script>

<style>
    h3 {
        margin-bottom: 5%;
    }
    span {
        width: 20em;
        height: 25em;
        border: 1px solid red;
    }
</style>