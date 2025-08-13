<template>
  <footer class="app-footer">
    <!-- Phần layout bên trái -->
    <div class="left-footer">
      <div class="left-app-logo">
        <!-- logo và tên-->
        <div class="app-logo-footer">

        </div>
        <p class="app-name-footer">LaslesVPN</p>
      </div>
      <div class="des-app-footer-info">
        <p style="color: #4F5665;">LaslesVPN is a private virtual network that has unique features and has high
          security.</p>
      </div>

      <p class="coppy-right-footer">©2025LaslesVPN</p>
    </div>

    <!-- Phần layout bên phải -->
    <div class="right-footer">
      <div class="header-right-footer">
        <a class="link-privacy" href="#">Chính sách Riêng tư và Bảo mật</a>
        <a class="link-policy" href="#">Điều khoản sử dụng ứng dụng</a>
      </div>
      <div class="info-right-link">
        <div class="container-link">
          <p class="title-link">Thông tin</p>
          <a class="link-item" href="#">About</a>
          <a class="link-item" href="#">Info</a>
          <a class="link-item" href="#">Download</a>
          <a class="link-item" href="#">Contact</a>
        </div>
        <div class="container-link">
          <p class="title-link">Liên kết</p>
          <a class="link-item" href="#">Google Play</a>
          <a class="link-item" href="#">Apple Store</a>
        </div>
        <div class="container-link">
          <p class="title-link">Khác</p>
          <a class="link-item" href="#">Trang chủ</a>
          <a class="link-item" href="#">Dịch vụ</a>
          <a class="link-item" href="#">Địa chỉ</a>
        </div>
      </div>
    </div>

  </footer>
</template>

<script setup>
// không cần gì đặc biệt
</script>

<style scoped>
.app-footer {
  display: flex;
  flex-direction: row;
  padding: 20px 20px;
  background-color: #F8F8F8;
}

.left-footer {
  width: 40%;
  display: block;
  padding-right: 80px;
}

.right-footer {
  width: 60%;
}

.right-footer {
  display: block;
  justify-content: flex-end;
}

.left-app-logo {
  display: flex;
  align-items: center;
}

.app-logo-footer {
  width: 50px;
  height: 50px;
  background-color: red;
}

.app-name-footer {
  margin-left: 10px;
  font-size: 24px;
  font-weight: 700;
}

.des-app-footer-info {
  margin-top: 15px;
}

.coppy-right-footer {
  margin-top: 40px;
  color: #AFB5C0;
}

/* right */
.header-right-footer {
  width: 100%;
  display: flex;
  align-items: end;
  justify-content: flex-end;
  padding: 10px;
}

a {
  text-decoration: none;
}

.link-privacy {
  font-size: 15px;
  font-weight: 500;
  color: #fc7373;
  margin-right: 30px;
}

.link-policy {
  font-size: 15px;
  font-weight: 500;
  color: #fc7373;
}

.container-link {
  display: block;
}

.info-right-link {
  margin-top: 20px;
  display: flex;
  justify-content: flex-end;
  gap: 150px;
  align-items: start;
}

.title-link {
  font-size: 16px;
  font-weight: 600;
}

.link-item {
  display: block;
  font-size: 15;
  color: #4F5665;
  margin-top: 5px;
}

@media (max-width: 768px) {
  .app-footer {
    flex-direction: column-reverse;
  }

  .right-footer,
  .left-footer {
    width: 100%;
  }

  .header-right-footer {
    padding: 0;
    margin: 0;
    justify-content: space-between;
  }

  .link-privacy {
    margin-right: 10px;
  }

  .info-right-link {
    flex-wrap: wrap;
    justify-content: space-between;
    gap: 0px;
    margin-top: 30px;
  }

  .left-footer {
    margin-top: 40px;
    padding: 0;
  }

  .coppy-right-footer {
    width: 100%;
    display: flex;
    margin-top: 40px;
    justify-content: center;
    align-items: center;
  }
}
</style>
