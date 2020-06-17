<template>
  <div id="app">
    <header class="top_text_shop">
		<h1>Cоставьте список покупок</h1>
	</header>
  <main>
      <div class="container">
        <h1 v-if="errMsg">{{errMsg}}</h1>
        <div class="form-group">
          <label for>Название</label>
          <input type="text" placeholder="Огурцы" class="form-control" v-model="product"/>
          <label for>Колличество</label>
          <input type="text" placeholder="2кг" class="form-control" v-model="numerus">
          <button v-if="isEdit" class="btn btn-primary mt-2" @click="onSaveEdit(id)">Сохранить</button>
          <button v-if="isEdit" class="btn btn-primary mt-2 ml-2" @click="EditModOff">Отмена</button>
          <button v-else class="btn btn-primary mt-2" @click="onSave">Сохранить</button>
        </div> 
        <div class="row mt-2" v-for="(list,index) in lists" :key="list.id">
          <div class="col">{{list.product}}</div>
          <div class="col">{{list.numerus}}</div>
          <div class="col">
            <button class="btn btn-danger" @click="onDelete(list.id)">Удалить</button>
          </div>
          <div class="col">
            <button class="btn btn-primary" @click="EditModOn(index)">Редактировать</button>
          </div>
        </div>
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

<script>
export default {
  name:"App",
  data: function(){
    return{
      lists:[],
      product:"",
      numerus:"",
      id:0,
      errMsg:"",
      isEdit:false
    };
  },
  components:{},
  methods:{
    async updateData(){
      try{
        let res = await this.$http.get("http://localhost:3000/lists");
        this.lists = await res.json();
        this.errMsg = ""; 
      }
      catch(e){
        console.error(e);
      }
    },
    async onSave(){
      let list ={
        product: this.product,
        numerus: this.numerus,
      };
      try{
        await this.$http.post("http://localhost:3000/lists",list);
        this.updateData();
      }
      catch(e){
        console.error(e);
      }
   },
    async onDelete(id){
      try{
        await this.$http.delete("http://localhost:3000/lists/" + id);
        this.updateData();
      }
      catch(e){
        console.error(e);
      }
    },
    EditModOn(index){
      this.product = this.lists[index].product;
      this.numerus = this.lists[index].numerus;
      this.id = this.lists[index].id;
      this.isEdit = true;
    },
    EditModOff(){
      this.product = "";
      this.numerus = "";
      this.id = 0;
      this.isEdit = false;
    },
    async onSaveEdit(id){
      let list = {
        product: this.product,
        numerus: this.numerus,
        id: this.id
      };
      try{
        await this.$http.put("http://localhost:3000/lists/"+id, list);
        this.updateData();
      }
      catch(e){
        console.error(e);
      }
    }
  },
  created(){
    this.updateData();
  } 
};
</script>