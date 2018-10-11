<template>
  <div> 
      <h1>Kaalu teisendamine</h1>
      <h4>Sisesta kaal kilogrammides:</h4>
      <input type="number" min="0" v-model="kg">
      <table v-if="kg !== 0">
          <tr>
              <td>Grammid</td>
              <td>{{convertKg(1000) + 'g' }}</td>
          </tr>
          <tr>
              <td>Naelad</td>
              <td> {{convertKg(2.20462262) + 'lb' }}</td>
          </tr>
          <tr>
              <td>Untsid</td>
              <td>{{convertKg(35.2739619) + 'oz' }}</td>
          </tr>
      </table>
  </div>
</template>

<script>
export default {
  name: 'Konverter',
  data (){
      return {
          kg: 0
      }
  },
  methods: {
    convertKg(multiplier){
            if(this.kg !== 0) {
            return (this.kg * multiplier).toFixed(2)
            } else {
                return 0 
            }
        return (this.kg !== 0) ? (this.kg * multiplier).toFixed(2) : 0
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    body {
        margin: 50px;
    }
</style>
