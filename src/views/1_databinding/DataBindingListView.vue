<template>
  <div>
    <div>
      <select name="" id="">
        <!-- key값은 리액트처럼 유일한 값이 와야한다. -->
        <option :value="city.code" :key="city.code" v-for="city in cities">
          {{ city.title }}
        </option>
      </select>
    </div>
    <div>
      <table>
        <thead>
          <tr>
            <th>제품명</th>
            <th>가격</th>
            <th>주문수량</th>
            <th>총 가격</th>
          </tr>
        </thead>
        <tbody>
          <!-- 만약 키값으로 쓸 값이 없으면 인덱스를 생성하면 된다.  -->
          <tr :key="'spl' + i" v-for="(spl, i) in shoppingList">
            <td>{{ spl.productName }}</td>
            <td>{{ spl.price }}</td>
            <td>
              <input
                type="number"
                v-model="spl.qty"
                @change="totalFunction(spl.price * spl.qty, spl.qty)"
              />
            </td>
            <td>
              {{ spl.price * spl.qty }}
            </td>
          </tr>
          <br />
        </tbody>
      </table>
      <h2>총 가격 {{ totalPrice }}</h2>
      <h2>총 주문수량 {{ totalQty }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      cities: [
        { title: '서울', code: '02' },
        { title: '부산', code: '051' },
        { title: '제주', code: '064' }
      ],
      shoppingList: [
        { productName: '핸드폰', price: 1320000, qty: 0 },
        { productName: '커피', price: 4500, qty: 0 },
        { productName: '선풍기', price: 29000, qty: 0 },
        { productName: '공책', price: 1000, qty: 0 },
        { productName: '치실', price: 8900, qty: 0 },
        { productName: '모니터', price: 359000, qty: 0 },
        { productName: '서랍', price: 32500, qty: 0 }
      ],
      totalPrice: 0,
      totalQty: 0
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    totalFunction(price, qty) {
      this.totalQty = 0
      for (let index = 0; index < this.shoppingList.length; index++) {
        this.totalQty += this.shoppingList[index].qty
      }

      this.totalPrice += price
    }
  }
}
</script>

<style></style>
