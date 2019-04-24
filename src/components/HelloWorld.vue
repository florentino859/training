<template>
	<div>
		<div>{{title}}</div>
		<ul>
			<li v-for="(product,index) in filteredProducts" :key="index" >
				<ProductItem :producto="product" :func="addToShopCart" ></ProductItem>
			</li>
		</ul>
		<div>{{total}}</div>
	</div>
</template>

<script>
import  ProductItem  from "./ProductItem.vue";
export default {
  name: 'ProductList',
  props: {

  },
  data(){
    return{
		title:"mis productos",
		total:0,
		products:[{
			name:"zapatos",
			price: "100.00",
			quantity:0
		},{
			name:"sillas",
			price: "2400.00",
			quantity:0
		},
		{
			name:"mesas",
			price: "300.00",
			quantity:0
		},
		{
			name:"sofas",
			price: "200.00",
			quantity:0
		}		
		],
		styleObject:{
			txtColor : true,
			bgColor: true,
			bgColorAzul: false
		}		
    }    
  },
  computed:{
		filteredProducts(){
			return this.products
			.filter((product,index) => (index >= 0));
		}
  },
  methods:{
		addToShopCart(price){
			this.total += parseFloat(price);			
		}	
  },
  components:{
	  ProductItem
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul{
	display: inline-grid;
}
.txtColor{
	color: white;
}

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
