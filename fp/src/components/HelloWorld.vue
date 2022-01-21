<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    


    <input type="text" v-model.number="operand1"/>
    <input type="text" v-model.number="operand2"/>

    = {{ result }}

    <hr/>
    <button @click="amount">+</button>
    <button @click="substraction">-</button>
    <button @click="divide">/</button>
    <button @click="multiply">*</button>

    <hr/>
    <input type="text" v-model.number="operand3"/>
    <input type="text" v-model.number="operand4"/>

    ={{ result2 }}
    <hr/>
    <button @click="pow">Возвести</button>
    <hr/>
    <input type="text" v-model.number="operand5"/>
    <input type="text" v-model.number="operand6"/>

    = {{ result3 }}
    <hr/>
    <button @click="floor">Поделить</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }, 
  data() {
    return {
      disabled: true,
      message: "",
      operand1:0,
      operand2:0,
      operand3:"Число возводимое в степень",
      operand4:"Степень",
      operand5:0,
      operand6:0,
      result: 0, 
      result2: 0,
      result3: 0
    }
  },
  methods: {
    pow () {
      this.result2 = Math.pow(this.operand3, this.operand4)
    },
    floor () {
      this.result3 = ~~(this.operand5 / this.operand6)
    },

    amount () {
      this.result = this.operand1 + this.operand2
    },
    substraction () {
      this.result = this.operand1 - this.operand2
    },
    divide () {
      this.result = this.operand1 / this.operand2
    },
    multiply () {
      this.result = this.operand1 * this.operand2
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
