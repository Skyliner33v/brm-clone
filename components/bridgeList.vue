<template>
  <v-card class="ma-4">
    <v-card-title class="blue-grey darken-3 headline"
      >Bridges
      <v-spacer />
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search Bridge ID"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    <v-data-table :headers="headers" :items="bridges" :search="search">
    </v-data-table>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      search: '',
      headers: [
        {
          text: 'Bridge ID',
          align: 'left',
          sortable: false,
          value: 'brgID',
          class: 'grey darken-2'
        },
        { text: 'Bridge Name', value: 'brgName', class: 'grey darken-2' },
        { text: 'District', value: 'district', class: 'grey darken-2' },
        { text: 'Facility Carried', value: 'facility', class: 'grey darken-2' },
        { text: 'County', value: 'county', class: 'grey darken-2' },
        { text: 'Owner', value: 'owner', class: 'grey darken-2' },
        { text: 'Year Built', value: 'yearBuilt', class: 'grey darken-2' }
      ],
      // TODO: Change this to an API call.  One Day...
      bridges: [
        {
          brgID: '539/850.25',
          brgName: 'STREAM 0553 CULVERT',
          district: 'SW Region',
          facility: 'SR 539',
          county: 'King County',
          owner: 'WA State',
          yearBuilt: 2008
        },
        {
          brgID: '520/5',
          brgName: '24TH AVE OVER SR 520',
          district: 'SW Region',
          facility: '24TH AVE',
          county: 'Pierce County',
          owner: 'WA State',
          yearBuilt: 1962
        },
        {
          brgID: '97/305',
          brgName: 'PESHASTIN CREEK',
          district: 'NW Region',
          facility: 'US 97',
          county: 'Whatcom County',
          owner: 'WA State',
          yearBuilt: 1956
        },
        {
          brgID: '2/306.25',
          brgName: 'DRY GULCH',
          district: 'NW Region',
          facility: 'US 2',
          county: 'Pierce County',
          owner: 'WA State',
          yearBuilt: 1994
        },
        {
          brgID: '5/104E',
          brgName: 'I-5 OVER DIKE ACCESS RD',
          district: 'OR Region',
          facility: 'I-5',
          county: 'Pierce County',
          owner: 'WA State',
          yearBuilt: 1955
        },
        {
          brgID: '5/534S-W',
          brgName: 'S-W RAMP OVER LUCILE ST',
          district: 'NW Region',
          facility: 'S-W RAMP',
          county: 'King County',
          owner: 'WA State',
          yearBuilt: 1967
        },
        {
          brgID: '101/358',
          brgName: 'RIVER RD OVER US 101',
          district: 'OR Region',
          facility: 'RIVER RD',
          county: 'Grays Harbor County',
          owner: 'WA State',
          yearBuilt: 1999
        },
        {
          brgID: '20/102FT',
          brgName: 'COUPEVILLE FERRY TERM',
          district: 'SW Region',
          facility: 'SR 20 EXTENSION',
          county: 'Lewis County',
          owner: 'WA State',
          yearBuilt: 1979
        },
        {
          brgID: '195/42',
          brgName: 'US 195 OVER ABANDONED RR',
          district: 'NW Region',
          facility: 'US 195',
          county: 'King County',
          owner: 'WA State',
          yearBuilt: 1964
        },
        {
          brgID: '90/172',
          brgName: 'PRATER RD OVER I-90',
          district: 'SC Region',
          facility: 'PRATER RD',
          county: 'Kittitas County',
          owner: 'WA State',
          yearBuilt: 1968
        },
        {
          brgID: '539/850.25',
          brgName: 'STREAM 0553 CULVERT',
          district: 'SW Region',
          facility: 'SR 539',
          county: 'King County',
          owner: 'WA State',
          yearBuilt: 2008
        },
        {
          brgID: '520/5',
          brgName: '24TH AVE OVER SR 520',
          district: 'SW Region',
          facility: '24TH AVE',
          county: 'Pierce County',
          owner: 'WA State',
          yearBuilt: 1962
        },
        {
          brgID: '97/305',
          brgName: 'PESHASTIN CREEK',
          district: 'NW Region',
          facility: 'US 97',
          county: 'Whatcom County',
          owner: 'WA State',
          yearBuilt: 1956
        },
        {
          brgID: '2/306.25',
          brgName: 'DRY GULCH',
          district: 'NW Region',
          facility: 'US 2',
          county: 'Pierce County',
          owner: 'WA State',
          yearBuilt: 1994
        },
        {
          brgID: '5/104E',
          brgName: 'I-5 OVER DIKE ACCESS RD',
          district: 'OR Region',
          facility: 'I-5',
          county: 'Pierce County',
          owner: 'WA State',
          yearBuilt: 1955
        },
        {
          brgID: '5/534S-W',
          brgName: 'S-W RAMP OVER LUCILE ST',
          district: 'NW Region',
          facility: 'S-W RAMP',
          county: 'King County',
          owner: 'WA State',
          yearBuilt: 1967
        }
      ]
    }
  }
}
</script>
