

<template>
    <div id='q-app'>
    <div class="q-pa-md" style="max-width: 350px">

      <q-card class="my-card">
        <q-card-section class="bg-primary text-white">
          <div class="text-h6">Alternative Routes to Leeds</div>
          <div class="text-subtitle2">Services are disrupted due to a signal failure at Doncaster</div>
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
          <q-item-label caption>{{journey.tickets}}</q-item-label>

            <q-expansion-item
              caption="Details"
            >
          <q-card>
              <img
                :src= "journey.imageURL"
                spinner-color="white"
                class="responsive"
              >
        </q-card>
      </q-expansion-item>

          
        </q-item-section>
      </q-item>
      </div>

    </q-list>
  </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  
  data () {
    return {
      
      accessURL:"https://maps.googleapis.com/maps/api/directions/json?origin=Kings+Cross&destination=Milton+Keynes&mode=transit&key=AIzaSyChzGyUhsXiYNJu2QxKCVY-tzvMADTWDZ4",
      opened: false,
      accessToken: "6120c81c-4b73-4901-a76a-f50da1b281f6",

      journeys: [
        
        {
        modes: "LNER > TransPennine Express",
        details: "via York",
        time: "2h 31m",
        imageURL: "statics/route1.png",
        tickets: "Tickets are accepted on 1st leg only"
        },


        {
        modes: "LNER > Northern",
        details: "via York",
        time: "2h 44m",
        imageURL: "statics/route3.png",
        tickets: "Tickets are accepted on 1st leg only"
        },

        {
        modes: "EMR > CrossCountry",
        details: "via Derby Midland",
        time: "3h 05m",
        imageURL: "statics/route2.png",
        tickets: "Tickets are accepted on the whole journey"
        }
      
      
      ]
    }
  }
}
</script>


