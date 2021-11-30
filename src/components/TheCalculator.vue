<template>
  <div>
    <div class="grid-container">
      <div id="history-screen">history screen</div>
      <div id="display">{{ display }}</div>
      
      <div id="clear" @click="clear()">AC</div>
      <div id="divide" class="operator">/</div>
      <div id="multiply" class="operator">*</div>
      <div id="subtract" class="operator">-</div>
      <div id="add" class="operator">+</div>
      <div id="equals">=</div>
      <div id="decimal">.</div>

      <div id="one" @click="input('1')">1</div>
      <div id="two" @click="input('2')">2</div>
      <div id="three" @click="input('3')">3</div>
      <div id="four" @click="input('4')">4</div>
      <div id="five" @click="input('5')">5</div>
      <div id="six" @click="input('6')">6</div>
      <div id="seven" @click="input('7')">7</div>
      <div id="eight" @click="input('8')">8</div>
      <div id="nine" @click="input('9')">9</div>
      <div id="zero" @click="input('0')">0</div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const display = ref('0');
    const input = (val) => {
      if (display.value === '0') {
        display.value = val;
      } else {
        display.value += val;
      }
      
    }
    const clear = () => {
      display.value = '0';
    }
    return {
      display,
      input,
      clear
    }
  }
  
}
</script>

<style scoped>
@font-face {
  font-family: 'Digital';
  src: url('//db.onlinewebfonts.com/t/8e22783d707ad140bffe18b2a3812529.eot');
  src: url('//db.onlinewebfonts.com/t/8e22783d707ad140bffe18b2a3812529.eot?#iefix')
      format('embedded-opentype'),
    url('//db.onlinewebfonts.com/t/8e22783d707ad140bffe18b2a3812529.woff2')
      format('woff2'),
    url('//db.onlinewebfonts.com/t/8e22783d707ad140bffe18b2a3812529.woff')
      format('woff'),
    url('//db.onlinewebfonts.com/t/8e22783d707ad140bffe18b2a3812529.ttf')
      format('truetype'),
    url('//db.onlinewebfonts.com/t/8e22783d707ad140bffe18b2a3812529.svg#Digital-7')
      format('svg');
}

#history-screen { 
  grid-area: history;
  background-color: black; 
  font-family: Digital;
  color: orange;
  font-size: 15px;
  /* height: 10px; */
}
#display { 
  grid-area: entry;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  font-family: Digital;
  background-color: black;
}
#clear { 
  grid-area: AC;
  background-color: brown;  
}
#divide { grid-area: divide; }
#multiply { grid-area: multi; }
#minus { grid-area: minus; }
#plus { grid-area: plus; }
#equals { 
  grid-area: equals; 
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: rgb(50, 91, 124);  
}
#decimal { grid-area: point; }
#zero { grid-area: oh; }
#one { grid-area: one; }
#two { grid-area: two; }
#three { grid-area: three; }
#four { grid-area: four; }
#five { grid-area: five; }
#six { grid-area: six; }
#seven { grid-area: seven; }
#eight { grid-area: eight; }
#nine { grid-area: nine; }

.grid-container {
  display: grid;
  grid-template-areas: 
    'history history history history'
    'entry entry entry entry'
    'AC AC divide multi'
    'seven eight nine minus'
    'four five six plus'
    'one two three equals'
    'oh oh point equals';
  grid-gap: 1px;
  background-color: black;
  padding: 5px;
}

.grid-container > div {
  background-color: rgb(78, 78, 78);
  color: white;
  text-align: center;
  padding: 20px;
  font-size: 20px;
  min-width: 75px;
}

.grid-container > .operator {
  background-color: rgb(173, 173, 173);
}
</style>