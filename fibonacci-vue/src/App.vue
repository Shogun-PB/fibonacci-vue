<template>
  <div>
    <!-- Formularz do wprowadzania numeru elementu ciągu -->
    <form @submit.prevent="calculateFibonacci">
      <label for="number">Podaj numer elementu ciągu:</label>
      <input v-model="number" type="number" id="number" required />
      <button type="submit">Oblicz</button>
    </form>

    <!-- Wyświetlenie wyniku i informacji dodatkowych -->
    <div v-if="result">
      <p>Nazwa programu: Fibonacci </p>
      <p> Imię i nazwisko autora: Patryk Bąk </p>
      <p> Numer grupy dziekańskiej: 1.1 </p>
      <p> Wynik: {{ result }} </p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number: 0,
      result: null,
    };
  },
  methods: {
    // Funkcja obliczająca wartość ciągu Fibonacciego
    calculateFibonacci() {
      // Sprawdzenie, czy podano poprawny numer elementu ciągu
      if (this.number < 0) {
        alert("Podaj wartość większą lub równą zero!");
        return;
      }

      // Algorytm obliczający wartość ciągu Fibonacciego (metoda rekurencyjna)
      const calculate = (n) => {
        if (n === 0 || n === 1) {
          return n;
        }
        return calculate(n - 1) + calculate(n - 2);
      };

      // Wywołanie funkcji obliczającej i zapisanie wyniku
      this.result = calculate(this.number);
    },
  },
};
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
