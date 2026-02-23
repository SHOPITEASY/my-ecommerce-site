# my-ecommerce-site
<div id="products"></div>

<script>

async function loadProducts(){

const { data } = await supabase
.from('products')
.select('*');

data.forEach(product => {

document.getElementById("products").innerHTML += `

<div>
<h3>${product.name}</h3>
<p>KES ${product.price}</p>
<img src="${product.image}" width="200">
</div>

`;

});

}

loadProducts();

</script>
