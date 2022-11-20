<template>
  <div id="contact">
    <h3 class="text-center mb-4">Thêm sản phẩm mới</h3>
    <div class="position-relative">
      <h4>Tên sản phẩm *</h4>
      <input placeholder="Nhập tên sản phẩm" type="text" v-model="this.title" />
      <span v-if="checkTitle" class="position-absolute"
        >Không được để trống Tên sản phẩm</span
      >
    </div>
    <div class="position-relative">
      <h4>Loại sản phẩm *</h4>
      <select placeholder="Chọn loại sản phẩm" class="w-100" style="height: 35px;" v-model="this.type">
        <option value="doan">Đồ ăn</option>
        <option value="douong">Đồ uống</option>
        <option value="giavi">Gia vị</option>
      </select>
      <span v-if="checkType" class="position-absolute" style="bottom: -18px ;"
        >Không được để trống loại sản phẩm</span
      >
    </div>
    <div class="position-relative">
      <h4>Giá tiền *</h4>
      <input placeholder="Nhập giá tiền" type="text" v-model="this.price" />
      <span v-if="checkPrice" class="position-absolute"
        >Không được để trống giá tiền và giá tiền phải > 0</span
      >
    </div>
    <div class="position-relative">
      <h4>Địa chỉ *</h4>
      <input placeholder="Nhập địa chỉ" type="text" v-model="this.address" />
      <span v-if="checkAdress" class="position-absolute"
        >Không được để trống địa chỉ</span
      >
    </div>
    <div class="position-relative">
      <h4>Link ảnh sản phẩm</h4>
      <input placeholder="Thêm link ảnh" type="text" v-model="this.image" />
    </div>    
    <div class="mt-4">
      <button @click="submit" name="submit" type="submit">Thêm sản phẩm</button>
    </div>
    <div class="text-center">{{ this.arlet }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      type: 'doan',
      price: 0,
      address: '',
      image: '',

      checkTitle: false,
      checkType: false,
      checkPrice: false,
      checkAdress: false,

      arlet: "",
    };
  },
  methods: {
    submit() {
      this.title === ""
        ? (this.checkTitle = true)
        : (this.checkTitle = false);

      this.type === ""
        ? (this.checkType = true)
        : (this.checkType = false);

      this.price === '' || +this.price <= 0
        ? (this.checkPrice = true)
        : (this.checkPrice = false);

      this.address === ""
        ? (this.checkAdress = true)
        : (this.checkAdress = false);

      if (
        !this.checkTitle &&
        !this.checkType &&
        !this.checkPrice &&
        !this.checkAdress
      ) {
        this.arlet = "Thêm sản phẩm thành công";
      }
    },
  },
};
</script>

<style scoped>
#contact div span {
  position: absolute;
  width: 100%;
  left: 10px;
  font-size: 12px;
  bottom: -5px;
  color: red;
}

#contact input[type="text"],
#contact input[type="email"],
#contact input[type="password"],
#contact input[type="url"],
#contact textarea,
#contact button[type="submit"] {
  font: 400 12px/16px "Roboto", Helvetica, Arial, sans-serif;
  margin-bottom: 15px !important;
}

#contact {
  background: #f9f9f9;
  padding: 25px;
  margin: 50px 0;
  box-shadow: 0 0 20px 0 rgba(0, 0, 0, 2%), 0 5px 5px 0 rgba(0, 0, 0, 24%);
  width: 650px;
  min-width: 400px;
  border-radius: 12px;
}

#contact h3 {
  display: block;
  font-size: 30px;
  font-weight: 300;
  margin-bottom: 10px;
}

#contact h4 {
  margin: 5px 0 15px;
  display: block;
  font-size: 13px;
  font-weight: 400;
}

div {
  border: medium none !important;
  margin: 0 0 25px;
  min-width: 100%;
  padding: 0;
  width: 100%;
}

#contact input[type="text"],
#contact input[type="email"],
#contact input[type="password"],
#contact input[type="url"],
#contact textarea {
  width: 100%;
  border: 1px solid #ccc;
  background: #fff;
  margin: 0 0 5px;
  padding: 10px;
}

#contact input[type="text"]:hover,
#contact input[type="email"]:hover,
#contact input[type="password"]:hover,
#contact input[type="url"]:hover,
#contact textarea:hover {
  transition: border-color 0.3s ease-in-out;
  border: 1px solid #aaa;
}

#contact textarea {
  height: 100px;
  max-width: 100%;
  resize: none;
}

#contact button[type="submit"] {
  cursor: pointer;
  width: 100%;
  border: none;
  background: #4caf50;
  color: #fff;
  margin: 0 0 5px;
  padding: 10px;
  font-size: 15px;
}

#contact button[type="submit"]:hover {
  background: #43a047;
  transition: background-color 0.3s ease-in-out;
}

#contact button[type="submit"]:active {
  box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.5);
}

.copyright {
  text-align: center;
}

#contact input:focus,
#contact textarea:focus {
  outline: 0;
  border: 1px solid #aaa;
}

::-webkit-input-placeholder {
  color: #888;
}

:-moz-placeholder {
  color: #888;
}

::-moz-placeholder {
  color: #888;
}

:-ms-input-placeholder {
  color: #888;
}
</style>
