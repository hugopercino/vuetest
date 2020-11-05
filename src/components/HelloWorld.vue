<template>
  <div>
    <h1>Estudos</h1>

    <div v-for="(input, index) in inputs" :key="index">
      <input type="checkbox" id="item" name="item" value="item">
      <label>{{input.item}}</label><br>
    </div>

    <h1>Itens pendentes: {{itemsLeng}}</h1>

    <form action="/action_page.php">
      <textarea id="w3review" name="w3review" rows="1" cols="50"  v-model="item">
        </textarea>
        <br><br>
        <input v-on:click="addItem" type="submit" value="Submit">
    </form>
  </div>
</template>

<script>
export default {

  data() {
    return {
        item: "",
        inputs: [],
        itemsLeng: 1,
        number2: 1
    }
  },
  methods: {
    addItem(event) {
        console.log(this.itemsLeng);
        this.inputs.push({
            item: this.item
        })
        event.preventDefault();

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
