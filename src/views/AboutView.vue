<template>
  <form class="contact-form" @submit.prevent="submitForm">
    <!-- Tên -->
    <div class="form-group">
      <label for="name">Tên *</label>
      <input type="text" id="name" v-model="form.name" placeholder="Nhập tên của bạn" />
      <p v-if="errors.name" class="error-text">{{ errors.name }}</p>
    </div>

    <!-- Xưng hô -->
    <div class="form-group">
      <label for="salutation">Xưng hô *</label>
      <select id="salutation" v-model="form.salutation">
        <option value="">Chọn xưng hô</option>
        <option value="Ông">Ông</option>
        <option value="Bà">Bà</option>
        <option value="Anh">Anh</option>
        <option value="Chị">Chị</option>
      </select>
      <p v-if="errors.salutation" class="error-text">{{ errors.salutation }}</p>
    </div>

    <!-- Email -->
    <div class="form-group">
      <label for="email">Email *</label>
      <input type="email" id="email" v-model="form.email" placeholder="Nhập email của bạn" />
      <p v-if="errors.email" class="error-text">{{ errors.email }}</p>
    </div>

    <!-- Loại yêu cầu -->
    <div class="form-group">
      <label for="requestType">Loại yêu cầu *</label>
      <select id="requestType" v-model="form.requestType">
        <option value="">Chọn loại yêu cầu</option>
        <option value="Hỗ Trợ và Trợ Giúp">Hỗ Trợ và Trợ Giúp</option>
        <option value="Hợp Tác">Hợp Tác</option>
        <option value="Công Việc">Công Việc</option>
      </select>
      <p v-if="errors.requestType" class="error-text">{{ errors.requestType }}</p>
    </div>

    <!-- Nội dung -->
    <div class="form-group">
      <label for="message">Nội dung *</label>
      <textarea id="message" v-model="form.message" placeholder="Nhập nội dung yêu cầu"></textarea>
      <p v-if="errors.message" class="error-text">{{ errors.message }}</p>
    </div>

    <!-- Nút gửi -->
    <button type="submit" class="submit-btn">Gửi liên hệ</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        salutation: "",
        email: "",
        requestType: "",
        message: ""
      },
      errors: {}
    };
  },
  methods: {
    validateForm() {
      this.errors = {};

      if (!this.form.name.trim()) {
        this.errors.name = "Vui lòng nhập tên.";
      }

      if (!this.form.salutation) {
        this.errors.salutation = "Vui lòng chọn xưng hô.";
      }

      if (!this.form.email.trim()) {
        this.errors.email = "Vui lòng nhập email.";
      } else if (!/\S+@\S+\.\S+/.test(this.form.email)) {
        this.errors.email = "Email không hợp lệ.";
      }

      if (!this.form.requestType) {
        this.errors.requestType = "Vui lòng chọn loại yêu cầu.";
      }

      if (!this.form.message.trim()) {
        this.errors.message = "Vui lòng nhập nội dung.";
      }

      return Object.keys(this.errors).length === 0;
    },
    submitForm() {
      if (this.validateForm()) {
        // Call API ở đây
        console.log("Form hợp lệ:", this.form);
        alert("Gửi liên hệ thành công!");
      }
    }
  }
};
</script>

<style scoped>
.contact-form {
  max-width: 500px;
  margin: auto;
  padding: 16px;
  background: #fff;
  border-radius: 8px;
}

.form-group {
  margin-bottom: 16px;
}

label {
  font-weight: bold;
  display: block;
  margin-bottom: 4px;
}

input,
select,
textarea {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.error-text {
  color: red;
  font-size: 13px;
  margin-top: 4px;
}

.submit-btn {
  background: #ff7373;
  color: #fff;
  padding: 10px 16px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.submit-btn:hover {
  background: #e86262;
}
</style>
