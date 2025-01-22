---
title: contact
date: 2025-01-22 18:59:36
layout: page
---

<div class="contact-container">
  <div class="qr-codes">
    <div class="qr-item">
      <img src="../images/home/wechat.jpeg" alt="微信公众号二维码" />
      <span>微信公众号</span>
    </div>
    <div class="qr-item">
      <img src="../images/home/xiaohongshu.jpeg" alt="小红书二维码" />
      <span>小红书</span>
    </div>
  </div>
  
  <div class="social-links">
    <a href="https://space.bilibili.com/你的ID" target="_blank">
      <i class="fab fa-bilibili"></i> Bilibili
    </a>
    <a href="https://www.douyin.com/user/你的ID" target="_blank">
      <i class="fab fa-tiktok"></i> 抖音
    </a>
    <a href="https://github.com/你的ID" target="_blank">
      <i class="fab fa-github"></i> GitHub
    </a>
    <a href="futurearray@outlook.com" target="_blank">
      <i class="fas fa-envelope"></i> Email
    </a>
  </div>
</div>

<style>
.contact-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

.qr-codes {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-bottom: 3rem;
}

.qr-item {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.qr-item img {
  width: 200px;
  height: 200px;
  border-radius: 10px;
  margin-bottom: 1rem;
}

.qr-item span {
  font-size: 1.1rem;
  color: #666;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 2rem;
  flex-wrap: wrap;
}

.social-links a {
  display: flex;
  align-items: center;
  padding: 0.8rem 1.5rem;
  background: #f5f5f5;
  border-radius: 5px;
  color: #333;
  text-decoration: none;
  transition: all 0.3s ease;
  margin: 0.5rem;
}

.social-links a:hover {
  background: #e0e0e0;
  transform: translateY(-2px);
}

.social-links i {
  margin-right: 0.5rem;
  font-size: 1.2rem;
}
</style>