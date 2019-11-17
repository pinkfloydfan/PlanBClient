

<template>

    <div class="q-pa-md" style="max-width: 350px">

      <q-card class="my-card">
        <q-card-section class="bg-primary text-white">
          <div class="text-h6">Alternative Routes to Bletchley</div>
          <div class="text-subtitle2">Services are disrupted due to a signal failure at Finsbury Park</div>
        </q-card-section>
        <q-separator ></q-separator>

    </q-card>

    <q-list bordered separator>

      <div v-for="journey in journeys">
      <q-item clickable v-ripple>
        <q-item-section>
          <q-item-label>{{journey.modes}}</q-item-label>
          <q-item-label caption>{{journey.details}}</q-item-label>
          <q-item-label caption>{{journey.time}}</q-item-label>

          
        </q-item-section>
      </q-item>
      </div>


    </q-list>
  </div>
</template>

<script>
export default {
  name: 'App',
  
  data () {
    return {
      
      accessURL:"https://maps.googleapis.com/maps/api/directions/json?origin=Kings+Cross&destination=Milton+Keynes&mode=transit&key=AIzaSyChzGyUhsXiYNJu2QxKCVY-tzvMADTWDZ4",

      accessToken: "6120c81c-4b73-4901-a76a-f50da1b281f6",

      journeys: [
        
        {
        modes: "Bus > Underground > Train",
        details: "26 to Finchley, Piccadilly to Finsbury Park, Thameslink to Bedford",
        time: "53 minutes"
        },

        {
        modes: "Underground > Train",
        details: "Northern to Woodside, Piccadilly to Finsbury Park, Thameslink to Bedford",
        time: "1 hr 6 minutes"
        }
      
      
      ]
    }
  }
}
</script>


