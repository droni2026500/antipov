<template>
<div id="app">
  <header class="top_text">
		<h1>Магазинчек</h1>
	</header>
  <main>
    <div class="all_shop">
					<img class="shop_img" src="../assets/shop.jpg" alt="shop">
					<p>Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet…
            Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… 
            Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet…
            Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet…
            Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet…
            Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit amet… Lorem ipsum dolor sit</p>
				</div>
  </main> 
  <footer>
    <section class="footer_content">
			<div class="about">
				<h4>Антипов Андрей Витальевич</h4>
        <b><a href="//router.vuejs.org/ru/" target="_blank">Нажми на меня</a></b>
			</div>
			<div class="support">
				<h4>181-362</h4>
        <b><a href="//webformyself.com/" target="_blank">И на меня(</a></b>
			</div>
			<div class="legal">
				<h4>17.06.2020</h4>
        <b><a href="//ru.vuejs.org/v2/guide/" target="_blank">А я?(((</a></b>
			</div>
		</section>
  </footer>
</div>
</template>

<style>
.shop_img {
	height: 20%;
	width: 20%;
	margin-right: 20px;
	float: left;
}
.all_shop {
	margin-bottom: 30px;
}
.all_shop p {
	text-align: justify;
	padding-right: 30px;
	font-size: 14px;
	word-wrap: break-word;

}
footer {
	background-color: #2780e3;
  margin-top: 10%;
}
.footer_content {

	margin: 10px 160px 10px 160px;
	display: flex;
	justify-content: center;
  padding: 30px 0;
}
.footer_content div {
  margin-right: 4%;
}

.footer_content div h4 {
  color: white;
}
.footer_content div a {
	color: black;
	padding-bottom: 10px;
  font-size: 15px;
}
</style>
