<template>
  <div class="overflow-auto">
    <b-container>
      <div class="text">
        <div class="left"><h3>المنتجات</h3></div>
        <div class="rigt">
          <button>
            اضافه منتج
            <i class="bx bx-plus"></i>
          </button>
        </div>
      </div>
      <hr />
      <b-form>
        <b-input type="text" placeholder="بحث بالاسم/ الباركود"></b-input>
      </b-form>
      <hr />
      <b-table
        
        id="my-table"
        :items="items"
        :fields="fields"
        :per-page="perPage"
        :current-page="currentPage"
        @change="currentinput"
      >
      <template #cell(Settings)="data">
        <button class="btn bot" @click="data">
        <span class="bx bxs-edit"></span>
        </button>
        <button class="btn bot">
        <span class="bx bx-message-alt-x"></span>
        </button>
      </template>
      </b-table>

      <div class="foot">
        <div class="current">
          <span>لكل صفحه</span>
          <input type="number" v-model="input" @input="currentinput" />
        </div>

        <b-pagination
          v-model="currentPage"
          :total-rows="rows"
          :per-page="perPage"
          aria-controls="my-table"
        ></b-pagination>

        <div class="foot_2">
          <input type="number" v-model="num">
          <button class="btn" @click="resnum">اذهب</button>
        </div>
        
      </div>
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: 7,
      perPage: 7,
      currentPage: 1,
      num:1,
      fields: [
        {
          key: "#",
        },
        {
          key: "الصوره",
        },
        {
          key: "الاسم",
        },
        {
          key: "الباركود",
        },
        {
          key: "القائمه",
        },
        {
          key: "السعر",
        },
        {
          key: "Settings",
          label:'الاعدادت'
        },
      ],

      items: [
        {
          "#": 1,
          الصوره: "لايوجد",
          الاسم: "Flintstone",
          الباركود: "111",
          القائمه: "يب يب",
          السعر: "33 ريال ",
          Settings: "icon icon",
        },
        {
          "#": 2,
          الصوره: "لايوجد",
          الاسم: "Flintstone",
          الباركود: "1112",
          القائمه: " يب",
          السعر: "323 ريال",
          Settings: "icon icon",
        },
        {
          "#": 3,
          الصوره: "لايوجد",
          الاسم: "Rubble",
          الباركود: "1113",
          القائمه: "ب يب",
          السعر: "303 ريال",
          Settings: "icon icon",
        },
        {
          "#": 4,
          الصوره: "لايوجد",
          الاسم: "Rubble",
          الباركود: "1114",
          القائمه: "يب ب",
          السعر: "333 ريال",
          Settings: "icon icon",
        },
        {
          "#": 5,
          الصوره: "لايوجد",
          الاسم: "Flintstone",
          الباركود: "1115",
          القائمه: "ب تيب",
          السعر: "3123 ريال",
          Settings: "icon icon",
        },
        {
          "#": 6,
          الصوره: "لايوجد",
          الاسم: "Rubble",
          الباركود: "1116",
          القائمه: "يب يب",
          السعر: "330 ريال ",
          Settings: "icon icon",
        },
        {
          "#": 7,
          الصوره: "لايوجد",
          الاسم: "Gazzoo",
          الباركود: "1117",
          القائمه: "قب يب",
          السعر: "3093 ريال ",
          Settings: "icon icon",
        },
        {
          "#": 8,
          الصوره: "لايوجد",
          الاسم: "Slate",
          الباركود: "1118",
          القائمه: "ب",
          السعر: "343 ريال",
          Settings: "icon icon",
        },
        {
          "#": 9,
          الصوره: "لايوجد",
          الاسم: "Slaghoople",
          الباركود: "1119",
          القائمه: "ي ب",
          السعر: "3343 ريال",
          Settings: "icon icon",
        },
        {
          "#": 10,
          الصوره: "لايوجد",
          الاسم: "Flintstone",
          الباركود: "111",
          القائمه: "يب يب",
          السعر: "33 ريال ",
          Settings: "icon icon",
        },
        {
          "#": 11,
          الصوره: "لايوجد",
          الاسم: "Flintstone",
          الباركود: "1112",
          القائمه: " يب",
          السعر: "323 ريال",
          Settings: "icon icon",
        },
        {
          "#": 12,
          الصوره: "لايوجد",
          الاسم: "Rubble",
          الباركود: "1113",
          القائمه: "ب يب",
          السعر: "303 ريال",
          Settings: "icon icon",
        },
        {
          "#": 13,
          الصوره: "لايوجد",
          الاسم: "Rubble",
          الباركود: "1114",
          القائمه: "يب ب",
          السعر: "333 ريال ",
          Settings: "icon icon",
        },
        {
          "#": 14,
          الصوره: "لايوجد",
          الاسم: "Flintstone",
          الباركود: "1115",
          القائمه: "ب تيب",
          السعر: "3123 ريال",
          Settings: "icon icon",
        },
        {
          "#": 15,
          الصوره: "لايوجد",
          الاسم: "Rubble",
          الباركود: "1116",
          القائمه: "يب يب",
          السعر: "330 ريال ",
          Settings: "icon icon",
        },
        {
          "#": 16,
          الصوره: "لايوجد",
          الاسم: "Gazzoo",
          الباركود: "1117",
          القائمه: "قب يب",
          السعر: "3093 ريال ",
          Settings: "icon icon",
        },
        {
          "#": 17,
          الصوره: "لايوجد",
          الاسم: "Slate",
          الباركود: "1118",
          القائمه: "ب",
          السعر: "343 ريال",
          Settings: "icon icon",
        },
        {
          "#": 18,
          الصوره: "لايوجد",
          الاسم: "Slaghoople",
          الباركود: "1119",
          القائمه: "ي ب",
          السعر: "3343 ريال",
          Settings: "icon icon",
        },
      ],
    };
  },
  computed: {
    rows() {
      return this.items.length;
    },
  },
  methods: {
    currentinput() {
      this.perPage = this.input;
    },
    resnum(){
        this.currentPage = this.num
      
    
  },
}
}
</script>
<style lang="scss">
html {
  direction: rtl;
}
.text {
  display: flex;
  justify-content: space-between;
  padding: 15px;
  button {
    border: none;
    background: #2196f3;
    color: #fff;
    font-weight: bold;
  }
}
.foot {
  display: flex;
  justify-content: space-between;
  padding: 5px;
  input {
    width: 25%;
  }
}
.bot span{
  font-size: 20px;
  color: #f44336;
}
.page-item:last-child .page-link,.page-item:first-child .page-link{display: none;}

</style>
