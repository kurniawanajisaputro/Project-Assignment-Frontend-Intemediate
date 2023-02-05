<template>
    <div class="container">
      <div>
        <title-component title="Semua Produk"></title-component>
        <hr>
          <product-cart-component :products="products" @updateCart="updateCart"/>
      </div>
      <div>
      <title-component title="Keranjang Belanja"></title-component>
      <hr>
        <cart-component :cart="cart" @updateCart="updateCart"></cart-component>
    </div>
      <hr>
      <b>Total Price : Rp. {{ total }}</b>
      <hr>
      <button-component text="Checkout" color="green" @emitClick="checkout"></button-component>
    </div>
  </template>
  <script>
  export default {
    data() {
        return {
            products: [
                { id: 1, name: "Indomie Goreng Rendang", description: "Masakan instan terenak di dunia", stock: 10, price: 3900 },
                { id: 2, name: "Mie Gelas Rendang", description: "Mie instan khusus anak kosan", stock: 5, price: 1500 },
                { id: 3, name: "Bakmi Mewah", description: "Kalau anak kosan jangan macam2 deh", stock: 80, price: 10000 },
            ],
            cart:[],
        }
    },
    computed: {
      total() {
        let total = 0;
        for (const item of this.cart) {
          total += item.quantity * item.product.price;
        }
        return total;
      }
    },
    methods: {
      updateCart(cart) {
        this.cart = cart
      },
      checkout() {
        if (this.cart.length === 0) {
          alert("Belanjaanmu Kosong");
          return;
        }
        alert(`Total: ${this.total}`);}}}
    </script>