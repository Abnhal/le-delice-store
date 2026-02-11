# le-delice-store
<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Le Dèlice - منصة الحلويات</title>
<meta name="description" content="منصة Le Dèlice - متاجر الحلويات الفاخرة">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>

<style>
:root {
    --bg-nude: #f4ece9;
    --main-brown: #5d4037;
    --light-brown: #8d6e63;
    --white: #ffffff;
    --card-shadow: rgba(93, 64, 55, 0.1);
    --success: #4CAF50;
    --error: #f44336;
    --warning: #ff9800;
    --store: #2196F3;
    --customer: #4CAF50;
    --admin: #9C27B0;
    --gold: #FFD700;
    --silver: #C0C0C0;
    --bronze: #CD7F32;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Tajawal', sans-serif;
    background-color: var(--bg-nude);
    color: var(--main-brown);
    direction: rtl;
    min-height: 100vh;
}

.hidden {
    display: none !important;
}

.page {
    min-height: 100vh;
    padding: 20px;
    display: flex;
    flex-direction: column;
}

.account-type-page,
.login-page,
.signup-page,
.otp-page,
.forgot-password-page,
.reset-password-page {
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #f5e6e0 0%, #f4ece9 100%);
}

.auth-card {
    background: var(--white);
    padding: 40px 30px;
    border-radius: 20px;
    box-shadow: 0 15px 40px rgba(93, 64, 55, 0.15);
    max-width: 500px;
    width: 100%;
    text-align: center;
    border: 1px solid #e8d9d1;
    position: relative;
    overflow: hidden;
}

.auth-card::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 5px;
    background: linear-gradient(90deg, var(--main-brown), var(--light-brown));
}

.auth-card h2 {
    font-family: 'Playfair Display', serif;
    margin-bottom: 30px;
    color: var(--main-brown);
    font-size: 28px;
}

.auth-card input,
.auth-card select {
    width: 100%;
    box-sizing: border-box;
    padding: 14px 20px;
    margin: 12px 0;
    border: 2px solid #e3d7d0;
    border-radius: 12px;
    background: #fefcfb;
    outline: none;
    color: var(--main-brown);
    font-family: 'Tajawal', sans-serif;
    font-size: 16px;
    transition: all 0.3s;
}

.auth-card input:focus,
.auth-card select:focus {
    border-color: var(--main-brown);
    box-shadow: 0 0 0 3px rgba(93, 64, 55, 0.1);
    background: #fff;
}

.auth-links {
    margin-top: 25px;
    padding-top: 20px;
    border-top: 1px solid #eee;
}

.link-btn {
    background: none;
    border: none;
    color: var(--main-brown);
    text-decoration: none;
    cursor: pointer;
    font-size: 15px;
    margin: 8px;
    padding: 8px 15px;
    border-radius: 8px;
    transition: all 0.3s;
    display: inline-flex;
    align-items: center;
    gap: 8px;
}

.link-btn:hover {
    background: rgba(93, 64, 55, 0.05);
    color: var(--light-brown);
    transform: translateY(-2px);
}

.account-type-options {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 25px;
    margin: 40px 0;
}

.account-type-card {
    background: white;
    padding: 30px 25px;
    border-radius: 20px;
    text-align: center;
    cursor: pointer;
    transition: all 0.4s;
    border: 2px solid transparent;
    box-shadow: 0 8px 25px rgba(93, 64, 55, 0.1);
    position: relative;
    overflow: hidden;
}

.account-type-card:hover {
    transform: translateY(-10px) scale(1.02);
    box-shadow: 0 20px 40px rgba(93, 64, 55, 0.2);
}

.account-type-card.store-option:hover { 
    border-color: var(--store); 
}
.account-type-card.customer-option:hover { 
    border-color: var(--customer); 
}
.account-type-card.admin-option:hover { 
    border-color: var(--admin); 
}

.account-icon {
    width: 90px;
    height: 90px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 20px;
    font-size: 36px;
    color: white;
    box-shadow: 0 8px 20px rgba(0,0,0,0.15);
    transition: all 0.3s;
}

.account-type-card:hover .account-icon {
    transform: scale(1.1) rotate(5deg);
}

.account-icon.store-icon { 
    background: linear-gradient(135deg, var(--store), #42a5f5); 
}
.account-icon.customer-icon { 
    background: linear-gradient(135deg, var(--customer), #66bb6a); 
}
.account-icon.admin-icon { 
    background: linear-gradient(135deg, var(--admin), #ba68c8); 
}

.features-list {
    text-align: right;
    margin: 20px 0;
    padding-right: 20px;
    list-style: none;
}

.features-list li {
    margin: 10px 0;
    font-size: 14px;
    color: var(--light-brown);
    position: relative;
    padding-right: 25px;
}

.features-list li::before {
    content: '✓';
    position: absolute;
    right: 0;
    color: var(--main-brown);
    font-weight: bold;
}

.otp-inputs {
    display: flex;
    justify-content: center;
    gap: 12px;
    margin: 25px 0;
}

.otp-digit {
    width: 55px;
    height: 55px;
    text-align: center;
    font-size: 24px;
    font-weight: bold;
    border: 3px solid #e3d7d0;
    border-radius: 12px;
    background: #fff;
    outline: none;
    transition: all 0.3s;
    color: var(--main-brown);
}

.otp-digit:focus {
    border-color: var(--main-brown);
    box-shadow: 0 0 0 4px rgba(93, 64, 55, 0.15);
    transform: scale(1.05);
}

.timer-container {
    margin: 20px 0;
    padding: 15px;
    background: linear-gradient(135deg, #fff3e0, #ffecb3);
    border-radius: 15px;
    border: 2px solid #ffcc80;
}

.timer {
    font-weight: bold;
    color: #e65100;
    font-size: 20px;
    font-family: 'Courier New', monospace;
    letter-spacing: 2px;
}

.navbar {
    background: var(--white);
    color: var(--main-brown);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 18px 5%;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 5px 20px rgba(93, 64, 55, 0.1);
    border-bottom: 1px solid #e8d9d1;
    backdrop-filter: blur(10px);
}

.brand-container {
    display: flex;
    flex-direction: column;
    gap: 5px;
}

.logo-text {
    font-family: 'Playfair Display', serif;
    font-size: 28px;
    font-weight: 700;
    line-height: 1;
    cursor: pointer;
    background: linear-gradient(90deg, var(--main-brown), var(--light-brown));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.logo-slogan {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--light-brown);
    font-weight: 500;
}

.nav-icons {
    display: flex;
    align-items: center;
    gap: 20px;
}

.user-type-badge {
    background: var(--light-brown);
    color: white;
    padding: 6px 15px;
    border-radius: 25px;
    font-size: 13px;
    font-weight: bold;
    box-shadow: 0 4px 12px rgba(93, 64, 55, 0.2);
    display: flex;
    align-items: center;
    gap: 8px;
}

.user-type-badge.store { 
    background: linear-gradient(135deg, var(--store), #42a5f5); 
}
.user-type-badge.customer { 
    background: linear-gradient(135deg, var(--customer), #66bb6a); 
}
.user-type-badge.admin { 
    background: linear-gradient(135deg, var(--admin), #ba68c8); 
}

.cart-btn,
.logout-btn,
.admin-btn,
.store-btn,
.back-btn,
.action-btn {
    cursor: pointer;
    background: linear-gradient(135deg, var(--main-brown), var(--light-brown));
    color: var(--white);
    padding: 12px 25px;
    border-radius: 12px;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 15px;
    border: none;
    font-family: 'Tajawal';
    text-decoration: none;
    font-weight: 600;
    box-shadow: 0 6px 20px rgba(93, 64, 55, 0.2);
}

.cart-btn:hover,
.logout-btn:hover,
.admin-btn:hover,
.store-btn:hover,
.back-btn:hover,
.action-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 25px rgba(93, 64, 55, 0.3);
}

.cart-count {
    background: var(--white);
    color: var(--main-brown);
    padding: 4px 10px;
    border-radius: 50%;
    font-size: 13px;
    font-weight: bold;
    min-width: 25px;
    min-height: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.container {
    width: 90%;
    max-width: 1400px;
    margin: 0 auto;
    flex: 1;
    padding: 30px 0;
}

.toast {
    position: fixed;
    bottom: 30px;
    right: 30px;
    background: var(--white);
    padding: 20px 25px;
    border-radius: 15px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.25);
    display: flex;
    align-items: center;
    gap: 15px;
    transform: translateY(100px);
    opacity: 0;
    transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    z-index: 10000;
    border-right: 6px solid var(--main-brown);
    min-width: 300px;
    max-width: 400px;
}

.toast.show {
    transform: translateY(0);
    opacity: 1;
}

.toast.success { border-color: var(--success); }
.toast.error { border-color: var(--error); }
.toast.warning { border-color: var(--warning); }
.toast.info { border-color: var(--store); }

.toast i {
    font-size: 22px;
}

.toast.success i { color: var(--success); }
.toast.error i { color: var(--error); }
.toast.warning i { color: var(--warning); }
.toast.info i { color: var(--store); }

.hero-section {
    background: linear-gradient(135deg, rgba(93, 64, 55, 0.9), rgba(141, 110, 99, 0.8));
    border-radius: 25px;
    padding: 60px 40px;
    color: white;
    text-align: center;
    margin-bottom: 40px;
    position: relative;
    overflow: hidden;
}

.hero-section::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background: url('https://images.unsplash.com/photo-1563729784474-d77dbb933a9e?w=1600&q=80') center/cover;
    opacity: 0.2;
    z-index: 0;
}

.hero-content {
    position: relative;
    z-index: 1;
}

.hero-content h1 {
    font-family: 'Playfair Display', serif;
    font-size: 48px;
    margin-bottom: 20px;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.hero-content p {
    font-size: 20px;
    margin-bottom: 30px;
    opacity: 0.9;
}

.search-container {
    max-width: 600px;
    margin: 0 auto 40px;
    position: relative;
}

.search-container input {
    width: 100%;
    padding: 18px 60px 18px 25px;
    border-radius: 50px;
    border: 3px solid #e3d7d0;
    background: var(--white);
    font-size: 17px;
    box-shadow: 0 10px 30px rgba(93, 64, 55, 0.15);
    outline: none;
    transition: all 0.3s;
}

.search-container input:focus {
    border-color: var(--main-brown);
    box-shadow: 0 15px 40px rgba(93, 64, 55, 0.25);
    transform: scale(1.02);
}

.search-container i {
    position: absolute;
    right: 25px;
    top: 50%;
    transform: translateY(-50%);
    color: var(--light-brown);
    font-size: 22px;
}

.products-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.product-card {
    background: var(--white);
    border-radius: 20px;
    overflow: hidden;
    box-shadow: 0 12px 30px rgba(93, 64, 55, 0.1);
    transition: all 0.4s;
    cursor: pointer;
    position: relative;
}

.product-card:hover {
    transform: translateY(-12px);
    box-shadow: 0 25px 50px rgba(93, 64, 55, 0.25);
}

.product-image {
    width: 100%;
    height: 240px;
    object-fit: cover;
    transition: transform 0.5s;
}

.product-card:hover .product-image {
    transform: scale(1.1);
}

.product-badge {
    position: absolute;
    top: 15px;
    left: 15px;
    background: linear-gradient(135deg, var(--store), #42a5f5);
    color: white;
    padding: 8px 18px;
    border-radius: 25px;
    font-size: 12px;
    font-weight: bold;
    z-index: 2;
}

.product-content {
    padding: 25px;
}

.product-title {
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 10px;
    color: var(--main-brown);
}

.product-description {
    color: var(--light-brown);
    font-size: 14px;
    line-height: 1.6;
    margin-bottom: 20px;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
}

.product-price {
    font-size: 24px;
    font-weight: 800;
    color: var(--main-brown);
    margin-bottom: 15px;
}

.original-price {
    text-decoration: line-through;
    color: #aaa;
    font-size: 18px;
    margin-right: 10px;
}

.product-actions {
    display: flex;
    gap: 10px;
    margin-top: 20px;
}

.btn-add-cart {
    flex: 1;
    padding: 12px;
    background: linear-gradient(135deg, var(--main-brown), var(--light-brown));
    color: white;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    font-weight: 600;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
}

.btn-add-cart:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(93, 64, 55, 0.3);
}

.btn-view {
    padding: 12px 20px;
    background: linear-gradient(135deg, #2196F3, #42a5f5);
    color: white;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    font-weight: 600;
    transition: all 0.3s;
}

.btn-view:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(33, 150, 243, 0.3);
}

.dashboard-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    margin: 40px 0;
}

.dashboard-card {
    background: var(--white);
    border-radius: 20px;
    padding: 30px;
    box-shadow: 0 12px 30px rgba(93, 64, 55, 0.1);
    transition: all 0.3s;
    border: 2px solid transparent;
}

.dashboard-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 40px rgba(93, 64, 55, 0.2);
    border-color: var(--main-brown);
}

.dashboard-card-header {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 25px;
}

.dashboard-icon {
    width: 70px;
    height: 70px;
    border-radius: 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 30px;
    color: white;
}

.dashboard-icon.orders { background: linear-gradient(135deg, #FF9800, #FFB74D); }
.dashboard-icon.products { background: linear-gradient(135deg, var(--customer), #66bb6a); }
.dashboard-icon.stores { background: linear-gradient(135deg, var(--store), #42a5f5); }
.dashboard-icon.customers { background: linear-gradient(135deg, var(--admin), #ba68c8); }
.dashboard-icon.settings { background: linear-gradient(135deg, #607D8B, #90A4AE); }
.dashboard-icon.delete { background: linear-gradient(135deg, var(--error), #ef5350); }

.dashboard-card h3 {
    font-size: 22px;
    color: var(--main-brown);
    margin-bottom: 5px;
}

.dashboard-card p {
    color: var(--light-brown);
    font-size: 14px;
}

.dashboard-stats {
    font-size: 36px;
    font-weight: 800;
    color: var(--main-brown);
    margin: 20px 0;
    text-align: center;
}

.dashboard-btn {
    width: 100%;
    padding: 15px;
    background: linear-gradient(135deg, var(--main-brown), var(--light-brown));
    color: white;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    font-weight: 600;
    font-size: 16px;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    margin-top: 20px;
}

.dashboard-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 25px rgba(93, 64, 55, 0.3);
}

.dashboard-btn.delete-btn {
    background: linear-gradient(135deg, var(--error), #ef5350);
}

.cart-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(93, 64, 55, 0.8);
    z-index: 2000;
    display: flex;
    justify-content: center;
    align-items: center;
    backdrop-filter: blur(10px);
    padding: 20px;
}

.cart-modal {
    background: var(--white);
    padding: 40px;
    border-radius: 25px;
    width: 100%;
    max-width: 600px;
    max-height: 90vh;
    overflow-y: auto;
    box-shadow: 0 25px 60px rgba(0,0,0,0.3);
}

.cart-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
    padding-bottom: 20px;
    border-bottom: 3px solid #f0e6e0;
}

.cart-header h2 {
    font-family: 'Playfair Display', serif;
    font-size: 32px;
    color: var(--main-brown);
    margin: 0;
}

.close-cart {
    background: none;
    border: none;
    font-size: 28px;
    cursor: pointer;
    color: var(--light-brown);
    transition: all 0.3s;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.close-cart:hover {
    background: rgba(93, 64, 55, 0.05);
    color: var(--main-brown);
    transform: rotate(90deg);
}

.cart-items {
    max-height: 400px;
    overflow-y: auto;
    padding-right: 10px;
}

.cart-item {
    display: flex;
    align-items: center;
    padding: 20px;
    background: #fefcfb;
    border-radius: 15px;
    margin-bottom: 15px;
    border: 2px solid #f0e6e0;
    transition: all 0.3s;
}

.cart-item:hover {
    border-color: var(--main-brown);
    transform: translateX(-5px);
}

.cart-item-image {
    width: 80px;
    height: 80px;
    border-radius: 12px;
    object-fit: cover;
    margin-left: 20px;
}

.cart-item-info {
    flex: 1;
}

.cart-item-name {
    font-weight: 700;
    font-size: 18px;
    color: var(--main-brown);
    margin-bottom: 5px;
}

.cart-item-store {
    color: var(--light-brown);
    font-size: 14px;
    margin-bottom: 10px;
}

.cart-item-price {
    font-weight: 700;
    color: var(--main-brown);
    font-size: 20px;
}

.cart-item-actions {
    display: flex;
    align-items: center;
    gap: 15px;
}

.quantity-control {
    display: flex;
    align-items: center;
    gap: 12px;
    background: #f5f0ed;
    padding: 8px 15px;
    border-radius: 25px;
}

.qty-btn {
    background: var(--white);
    border: 2px solid #e3d7d0;
    width: 35px;
    height: 35px;
    border-radius: 50%;
    cursor: pointer;
    font-weight: bold;
    color: var(--main-brown);
    font-size: 18px;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
}

.qty-btn:hover {
    background: var(--main-brown);
    color: white;
    border-color: var(--main-brown);
    transform: scale(1.1);
}

.qty-val {
    font-weight: bold;
    min-width: 30px;
    text-align: center;
    font-size: 18px;
}

.remove-item {
    background: linear-gradient(135deg, var(--error), #ef5350);
    color: white;
    border: none;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s;
}

.remove-item:hover {
    transform: rotate(90deg) scale(1.1);
}

.cart-summary {
    margin-top: 30px;
    padding-top: 25px;
    border-top: 3px solid #f0e6e0;
}

.cart-total {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 25px;
}

.cart-total span {
    font-size: 24px;
    font-weight: 800;
    color: var(--main-brown);
}

.cart-total .amount {
    font-size: 32px;
    color: var(--main-brown);
}

.cart-actions {
    display: flex;
    gap: 15px;
}

.btn-clear-cart {
    flex: 1;
    padding: 16px;
    background: linear-gradient(135deg, #607D8B, #90A4AE);
    color: white;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    font-weight: 600;
    font-size: 16px;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
}

.btn-clear-cart:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 25px rgba(96, 125, 139, 0.3);
}

.btn-checkout {
    flex: 2;
    padding: 16px;
    background: linear-gradient(135deg, #25D366, #128C7E);
    color: white;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    font-weight: 600;
    font-size: 18px;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
}

.btn-checkout:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 30px rgba(37, 211, 102, 0.4);
}

.empty-cart {
    text-align: center;
    padding: 60px 20px;
    color: var(--light-brown);
}

.empty-cart i {
    font-size: 80px;
    margin-bottom: 20px;
    opacity: 0.3;
}

.empty-cart h3 {
    font-size: 24px;
    color: var(--main-brown);
    margin-bottom: 10px;
}

.footer {
    background: linear-gradient(135deg, var(--main-brown), var(--light-brown));
    padding: 50px 5% 30px;
    color: white;
    text-align: center;
    margin-top: auto;
}

.footer-content {
    max-width: 1200px;
    margin: 0 auto;
}

.footer-logo {
    font-family: 'Playfair Display', serif;
    font-size: 32px;
    margin-bottom: 10px;
    font-weight: 700;
}

.footer-slogan {
    font-size: 16px;
    opacity: 0.9;
    margin-bottom: 30px;
}

.footer-links {
    display: flex;
    justify-content: center;
    gap: 40px;
    margin-bottom: 40px;
    flex-wrap: wrap;
}

.footer-link {
    color: white;
    text-decoration: none;
    font-size: 15px;
    opacity: 0.8;
    transition: all 0.3s;
    padding: 8px 16px;
    border-radius: 8px;
}

.footer-link:hover {
    opacity: 1;
    background: rgba(255,255,255,0.1);
    transform: translateY(-3px);
}

.footer-copyright {
    font-size: 13px;
    opacity: 0.7;
    padding-top: 20px;
    border-top: 1px solid rgba(255,255,255,0.2);
}

.product-details-modal {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(93, 64, 55, 0.9);
    z-index: 2000;
    display: flex;
    justify-content: center;
    align-items: center;
    backdrop-filter: blur(10px);
    padding: 20px;
}

.details-content {
    background: var(--white);
    border-radius: 25px;
    width: 100%;
    max-width: 900px;
    max-height: 90vh;
    overflow-y: auto;
    position: relative;
}

.close-details {
    position: absolute;
    top: 20px;
    left: 20px;
    background: var(--white);
    border: none;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 24px;
    color: var(--main-brown);
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
    transition: all 0.3s;
}

.close-details:hover {
    background: var(--main-brown);
    color: white;
    transform: rotate(90deg);
}

.details-image {
    width: 100%;
    height: 400px;
    object-fit: cover;
}

.details-info {
    padding: 40px;
}

.details-title {
    font-family: 'Playfair Display', serif;
    font-size: 36px;
    color: var(--main-brown);
    margin-bottom: 15px;
}

.details-store {
    color: var(--store);
    font-size: 18px;
    font-weight: 600;
    margin-bottom: 25px;
    display: flex;
    align-items: center;
    gap: 10px;
}

.details-description {
    color: var(--light-brown);
    font-size: 17px;
    line-height: 1.8;
    margin-bottom: 30px;
}

.details-price-section {
    display: flex;
    align-items: center;
    gap: 30px;
    margin-bottom: 30px;
    padding: 25px;
    background: #fefcfb;
    border-radius: 20px;
    border: 2px solid #f0e6e0;
}

.details-price {
    font-size: 42px;
    font-weight: 800;
    color: var(--main-brown);
}

.details-actions {
    display: flex;
    gap: 20px;
}

.btn-add-to-cart-details {
    flex: 1;
    padding: 20px;
    background: linear-gradient(135deg, var(--main-brown), var(--light-brown));
    color: white;
    border: none;
    border-radius: 15px;
    cursor: pointer;
    font-weight: 600;
    font-size: 18px;
    transition: all 0.3s;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
}

.btn-add-to-cart-details:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 30px rgba(93, 64, 55, 0.4);
}

@media (max-width: 768px) {
    .account-type-options {
        grid-template-columns: 1fr;
    }
    
    .auth-card {
        padding: 30px 20px;
    }
    
    .hero-content h1 {
        font-size: 36px;
    }
    
    .products-grid {
        grid-template-columns: 1fr;
    }
    
    .dashboard-grid {
        grid-template-columns: 1fr;
    }
    
    .footer-links {
        flex-direction: column;
        gap: 20px;
    }
    
    .details-price-section {
        flex-direction: column;
        gap: 20px;
    }
    
    .details-actions {
        flex-direction: column;
    }
}

@media (max-width: 480px) {
    .auth-card {
        padding: 25px 15px;
    }
    
    .otp-digit {
        width: 45px;
        height: 45px;
        font-size: 20px;
    }
    
    .navbar {
        padding: 15px 20px;
    }
    
    .nav-icons {
        gap: 10px;
    }
}
</style>
</head>

<body>
<div id="toastContainer"></div>

<!-- صفحة اختيار نوع الحساب -->
<div id="accountTypePage" class="page account-type-page">
    <div class="auth-container">
        <div class="auth-header">
            <h1 style="font-family: 'Playfair Display', serif; font-size: 48px; margin-bottom: 20px; color: var(--main-brown);">Le Dèlice</h1>
            <p style="font-size: 18px; color: var(--light-brown);">منصة متاجر الحلويات الفاخرة</p>
        </div>
        
        <div class="account-type-options">
            <div class="account-type-card store-option" onclick="showStoreSignup()">
                <div class="account-icon store-icon"><i class="fas fa-store"></i></div>
                <h3>متجر</h3>
                <p>إدارة منتجاتك واستقبال الطلبات</p>
                <ul class="features-list">
                    <li>إضافة منتجات وتصنيفات</li>
                    <li>استقبال طلبات على واتساب</li>
                    <li>إدارة المخزون</li>
                    <li>تقييمات العملاء</li>
                </ul>
            </div>
            
            <div class="account-type-card customer-option" onclick="showCustomerSignup()">
                <div class="account-icon customer-icon"><i class="fas fa-user"></i></div>
                <h3>عميل</h3>
                <p>تصفح واطلب أفضل الحلويات</p>
                <ul class="features-list">
                    <li>تصفح المتاجر والمنتجات</li>
                    <li>طلب المنتجات المفضلة</li>
                    <li>تقييم المنتجات</li>
                    <li>متابعة الطلبات</li>
                </ul>
            </div>
            
            <div class="account-type-card admin-option" onclick="showAdminLogin()">
                <div class="account-icon admin-icon"><i class="fas fa-user-shield"></i></div>
                <h3>إدارة النظام</h3>
                <p>إشراف كامل على المنصة</p>
                <ul class="features-list">
                    <li>إدارة جميع المتاجر</li>
                    <li>مراقبة المستخدمين</li>
                    <li>تقارير وإحصائيات</li>
                    <li>دعم المتاجر</li>
                </ul>
            </div>
        </div>
        
        <div class="auth-links">
            <p style="color: var(--light-brown); font-size: 16px; margin-bottom: 15px;">هل لديك حساب بالفعل؟</p>
            <button class="action-btn" onclick="showLoginPage()">
                <i class="fas fa-sign-in-alt"></i> تسجيل الدخول
            </button>
        </div>
    </div>
</div>

<!-- صفحة تسجيل الدخول -->
<div id="loginPage" class="page login-page hidden">
    <div class="auth-card">
        <h2>تسجيل الدخول</h2>
        <select id="loginType">
            <option value="">اختر نوع الحساب</option>
            <option value="customer">عميل</option>
            <option value="store">متجر</option>
            <option value="admin">إدارة</option>
        </select>
        <input type="email" id="loginEmail" placeholder="البريد الإلكتروني">
        <input type="password" id="loginPass" placeholder="كلمة المرور">
        
        <div style="text-align: left; margin: 15px 0;">
            <button class="link-btn" onclick="showForgotPasswordPage()">
                <i class="fas fa-key"></i> نسيت كلمة المرور؟
            </button>
        </div>
        
        <button class="action-btn" onclick="login()">
            <i class="fas fa-sign-in-alt"></i> دخول
        </button>
        
        <div class="auth-links">
            <button class="link-btn" onclick="showAccountTypePage()">
                <i class="fas fa-arrow-right"></i> العودة لصفحة الاختيار
            </button>
        </div>
    </div>
</div>

<!-- صفحة نسيت كلمة المرور -->
<div id="forgotPasswordPage" class="page forgot-password-page hidden">
    <div class="auth-card">
        <h2>استعادة كلمة المرور</h2>
        <select id="forgotType">
            <option value="">اختر نوع الحساب</option>
            <option value="customer">عميل</option>
            <option value="store">متجر</option>
        </select>
        <input type="email" id="forgotEmail" placeholder="أدخل البريد الإلكتروني">
        
        <div style="margin: 25px 0; padding: 20px; background: linear-gradient(135deg, #fff3e0, #ffecb3); border-radius: 15px; text-align: center; border: 2px solid #ffcc80;">
            <i class="fas fa-info-circle" style="color: #FF9800; font-size: 24px; margin-bottom: 10px;"></i>
            <p style="font-size: 15px; color: var(--light-brown);">
                سنرسل رمز تحقق إلى بريدك الإلكتروني لاستعادة كلمة المرور
            </p>
        </div>
        
        <button class="action-btn" onclick="sendPasswordResetOTP()" style="background: linear-gradient(135deg, #FF9800, #FFB74D);">
            <i class="fas fa-paper-plane"></i> إرسال رمز التحقق
        </button>
        
        <div class="auth-links">
            <button class="link-btn" onclick="showLoginPage()">
                <i class="fas fa-arrow-right"></i> العودة لتسجيل الدخول
            </button>
        </div>
    </div>
</div>

<!-- صفحة إعادة تعيين كلمة المرور -->
<div id="resetPasswordPage" class="page reset-password-page hidden">
    <div class="auth-card">
        <h2>إعادة تعيين كلمة المرور</h2>
        
        <div style="margin-bottom: 25px; text-align: center;">
            <i class="fas fa-key" style="font-size: 60px; color: var(--light-brown); margin-bottom: 20px; background: linear-gradient(135deg, #fff3e0, #ffecb3); width: 100px; height: 100px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 20px;"></i>
            <p style="color: var(--main-brown); font-size: 16px; margin-bottom: 10px;">رمز التحقق مرسل إلى:</p>
            <p id="resetEmailText" style="color: var(--main-brown); font-weight: bold; font-size: 20px;"></p>
        </div>
        
        <div class="otp-inputs">
            <input type="text" maxlength="1" class="otp-digit" data-index="0" oninput="moveToNext(this,1)" onkeyup="handleOTPInput(event,0)">
            <input type="text" maxlength="1" class="otp-digit" data-index="1" oninput="moveToNext(this,2)" onkeyup="handleOTPInput(event,1)">
            <input type="text" maxlength="1" class="otp-digit" data-index="2" oninput="moveToNext(this,3)" onkeyup="handleOTPInput(event,2)">
            <input type="text" maxlength="1" class="otp-digit" data-index="3" oninput="moveToNext(this,4)" onkeyup="handleOTPInput(event,3)">
            <input type="text" maxlength="1" class="otp-digit" data-index="4" oninput="moveToNext(this,5)" onkeyup="handleOTPInput(event,4)">
            <input type="text" maxlength="1" class="otp-digit" data-index="5" oninput="moveToNext(this,5)" onkeyup="handleOTPInput(event,5)">
        </div>
        
        <div class="timer-container">
            <div class="timer" id="resetTimer">05:00</div>
        </div>
        
        <input type="password" id="newPassword" placeholder="كلمة المرور الجديدة">
        <input type="password" id="confirmNewPassword" placeholder="تأكيد كلمة المرور الجديدة">
        
        <button class="action-btn" id="resetPasswordBtn" onclick="resetPassword()" disabled style="background: linear-gradient(135deg, var(--success), #66bb6a);">
            <i class="fas fa-sync-alt"></i> تغيير كلمة المرور
        </button>
        <button class="action-btn" id="resendResetOTPBtn" onclick="resendResetOTP()" style="background: linear-gradient(135deg, var(--light-brown), #a1887f); margin-top: 15px;" disabled>
            <i class="fas fa-redo"></i> إعادة إرسال الرمز
        </button>
        
        <div class="auth-links">
            <button class="link-btn" onclick="showLoginPage()">
                <i class="fas fa-arrow-right"></i> العودة لتسجيل الدخول
            </button>
        </div>
    </div>
</div>

<!-- صفحة التسجيل كمحل -->
<div id="storeSignupPage" class="page signup-page hidden">
    <div class="auth-card">
        <h2>تسجيل متجر جديد</h2>
        <input type="text" id="storeOwnerName" placeholder="اسم المالك">
        <input type="text" id="storeName" placeholder="اسم المتجر">
        <input type="email" id="storeEmail" placeholder="البريد الإلكتروني">
        <input type="tel" id="storePhone" placeholder="رقم الجوال (واتساب)">
        <input type="password" id="storePassword" placeholder="كلمة المرور">
        <input type="password" id="storeConfirmPassword" placeholder="تأكيد كلمة المرور">
        
        <button class="action-btn" onclick="registerStore()" style="background: linear-gradient(135deg, var(--store), #42a5f5);">
            <i class="fas fa-store"></i> تسجيل المتجر
        </button>
        
        <div class="auth-links">
            <button class="link-btn" onclick="showAccountTypePage()">
                <i class="fas fa-arrow-right"></i> العودة لصفحة الاختيار
            </button>
            <span style="color: var(--light-brown); margin: 0 10px;">لديك حساب؟</span>
            <button class="link-btn" onclick="showLoginPage()">
                <i class="fas fa-sign-in-alt"></i> تسجيل الدخول
            </button>
        </div>
    </div>
</div>

<!-- صفحة التسجيل كعميل -->
<div id="customerSignupPage" class="page signup-page hidden">
    <div class="auth-card">
        <h2>تسجيل حساب عميل</h2>
        <input type="text" id="customerName" placeholder="الاسم الكامل">
        <input type="email" id="customerEmail" placeholder="البريد الإلكتروني">
        <input type="password" id="customerPassword" placeholder="كلمة المرور">
        <input type="password" id="customerConfirmPassword" placeholder="تأكيد كلمة المرور">
        
        <button class="action-btn" onclick="registerCustomer()" style="background: linear-gradient(135deg, var(--customer), #66bb6a);">
            <i class="fas fa-user-plus"></i> تسجيل العميل
        </button>
        
        <div class="auth-links">
            <button class="link-btn" onclick="showAccountTypePage()">
                <i class="fas fa-arrow-right"></i> العودة لصفحة الاختيار
            </button>
            <span style="color: var(--light-brown); margin: 0 10px;">لديك حساب؟</span>
            <button class="link-btn" onclick="showLoginPage()">
                <i class="fas fa-sign-in-alt"></i> تسجيل الدخول
            </button>
        </div>
    </div>
</div>

<!-- صفحة دخول الإدارة -->
<div id="adminLoginPage" class="page login-page hidden">
    <div class="auth-card">
        <h2>دخول لوحة الإدارة</h2>
        <input type="text" id="adminUsername" placeholder="اسم المستخدم">
        <input type="password" id="adminPassword" placeholder="كلمة المرور">
        
        <button class="action-btn" onclick="loginAdmin()" style="background: linear-gradient(135deg, var(--admin), #ba68c8);">
            <i class="fas fa-user-shield"></i> دخول لوحة التحكم
        </button>
        
        <div class="auth-links">
            <button class="link-btn" onclick="showAccountTypePage()">
                <i class="fas fa-arrow-right"></i> العودة لصفحة الاختيار
            </button>
        </div>
    </div>
</div>

<!-- صفحة التحقق OTP -->
<div id="otpPage" class="page otp-page hidden">
    <div class="auth-card">
        <h2>تأكيد الحساب</h2>
        
        <div style="text-align: center; margin: 30px 0;">
            <i class="fas fa-envelope" style="font-size: 60px; color: var(--light-brown); margin-bottom: 20px; background: linear-gradient(135deg, #e3f2fd, #bbdefb); width: 100px; height: 100px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 25px;"></i>
            <p style="color: var(--light-brown); font-size: 16px; margin-bottom: 10px;">تم إرسال رمز التحقق إلى:</p>
            <p id="otpEmail" style="font-weight: bold; color: var(--main-brown); font-size: 22px; margin: 15px 0;"></p>
        </div>
        
        <div class="otp-inputs">
            <input type="text" maxlength="1" class="otp-digit" data-index="0" oninput="moveToNext(this,1)" onkeyup="handleOTPInput(event,0)">
            <input type="text" maxlength="1" class="otp-digit" data-index="1" oninput="moveToNext(this,2)" onkeyup="handleOTPInput(event,1)">
            <input type="text" maxlength="1" class="otp-digit" data-index="2" oninput="moveToNext(this,3)" onkeyup="handleOTPInput(event,2)">
            <input type="text" maxlength="1" class="otp-digit" data-index="3" oninput="moveToNext(this,4)" onkeyup="handleOTPInput(event,3)">
            <input type="text" maxlength="1" class="otp-digit" data-index="4" oninput="moveToNext(this,5)" onkeyup="handleOTPInput(event,4)">
            <input type="text" maxlength="1" class="otp-digit" data-index="5" oninput="moveToNext(this,5)" onkeyup="handleOTPInput(event,5)">
        </div>
        
        <div class="timer-container">
            <div class="timer" id="otpTimer">05:00</div>
        </div>
        
        <button class="action-btn" id="verifyOTPBtn" onclick="verifyOTP()" disabled style="background: linear-gradient(135deg, var(--success), #66bb6a);">
            <i class="fas fa-check-circle"></i> تأكيد الحساب
        </button>
        <button class="action-btn" id="resendOTPBtn" onclick="resendOTP()" style="background: linear-gradient(135deg, var(--light-brown), #a1887f); margin-top: 15px;" disabled>
            <i class="fas fa-redo"></i> إعادة إرسال الرمز
        </button>
        
        <div class="auth-links">
            <button class="link-btn" onclick="goBackFromOTP()">
                <i class="fas fa-arrow-right"></i> العودة
            </button>
        </div>
    </div>
</div>

<!-- الصفحة الرئيسية -->
<div id="mainPage" class="page main-page hidden">
    <nav class="navbar">
        <div class="brand-container">
            <div class="logo-text" onclick="showHomePage()">Le Dèlice</div>
            <div class="logo-slogan">منصة متاجر الحلويات</div>
        </div>
        <div class="nav-icons">
            <span id="userInfo" style="font-size: 15px; font-weight: 600; color: var(--main-brown);"></span>
            <span id="userTypeBadge" class="user-type-badge hidden"></span>
            <button class="cart-btn" id="cartBtn" onclick="toggleCart()">
                <i class="fas fa-shopping-bag"></i>
                <span class="cart-count" id="cartCount">0</span>
            </button>
            <button class="store-btn hidden" id="storeBtn" onclick="showStoreDashboard()">
                <i class="fas fa-store"></i> لوحة المتجر
            </button>
            <button class="admin-btn hidden" id="adminBtn" onclick="showAdminDashboard()">
                <i class="fas fa-cog"></i> لوحة التحكم
            </button>
            <button class="logout-btn" onclick="logout()">
                <i class="fas fa-sign-out-alt"></i> خروج
            </button>
        </div>
    </nav>
    
    <div class="container">
        <div class="hero-section">
            <div class="hero-content">
                <h1>اكتشف عالم الحلويات الفاخرة</h1>
                <p>أفضل المتاجر وألذ المنتجات في مكان واحد</p>
                <div class="search-container">
                    <i class="fas fa-search"></i>
                    <input type="text" id="searchInput" placeholder="ابحث عن منتجات أو متاجر...">
                </div>
            </div>
        </div>
        
        <h2 style="text-align: center; margin: 50px 0 30px; font-family: 'Playfair Display'; font-size: 36px; color: var(--main-brown);">المتاجر المميزة</h2>
        <div id="storesGrid" class="products-grid"></div>
        
        <h2 style="text-align: center; margin: 60px 0 30px; font-family: 'Playfair Display'; font-size: 36px; color: var(--main-brown);">أحدث المنتجات</h2>
        <div id="productsGrid" class="products-grid"></div>
    </div>
    
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-logo">Le Dèlice</div>
            <div class="footer-slogan">منصة متاجر الحلويات الفاخرة</div>
            <div class="footer-links">
                <a href="#" class="footer-link">عن المنصة</a>
                <a href="#" class="footer-link">الشروط والأحكام</a>
                <a href="#" class="footer-link">سياسة الخصوصية</a>
                <a href="#" class="footer-link">الدعم الفني</a>
                <a href="#" class="footer-link">اتصل بنا</a>
            </div>
            <div class="footer-copyright">©️ 2024 Le Dèlice - جميع الحقوق محفوظة</div>
        </div>
    </footer>
</div>

<!-- سلة التسوق -->
<div id="cartModal" class="cart-overlay hidden">
    <div class="cart-modal">
        <div class="cart-header">
            <h2>سلة التسوق</h2>
            <button class="close-cart" onclick="toggleCart()">×</button>
        </div>
        
        <div id="cartItems" class="cart-items"></div>
        
        <div class="cart-summary">
            <div class="cart-total">
                <span>المجموع الكلي:</span>
                <span class="amount" id="cartTotalAmount">0 ريال</span>
            </div>
            
            <div class="cart-actions">
                <button class="btn-clear-cart" onclick="clearCart()">
                    <i class="fas fa-trash-alt"></i> إفراغ السلة
                </button>
                <button class="btn-checkout" onclick="checkoutWhatsApp()">
                    <i class="fab fa-whatsapp"></i> إتمام الطلب عبر واتساب
                </button>
            </div>
        </div>
    </div>
</div>

<!-- تفاصيل المنتج -->
<div id="productDetailsModal" class="product-details-modal hidden">
    <div class="details-content">
        <button class="close-details" onclick="closeProductDetails()">×</button>
        <img id="detailsImage" class="details-image" src="" alt="">
        <div class="details-info">
            <h2 id="detailsTitle" class="details-title"></h2>
            <div id="detailsStore" class="details-store"></div>
            <p id="detailsDescription" class="details-description"></p>
            
            <div class="details-price-section">
                <div>
                    <div id="detailsPrice" class="details-price"></div>
                    <div id="detailsOriginalPrice" class="original-price" style="display: none;"></div>
                </div>
                <div class="details-quantity">
                    <label>الكمية:</label>
                    <div class="quantity-control">
                        <button class="qty-btn" onclick="changeProductQuantity(-1)">-</button>
                        <span id="productQuantity" class="qty-val">1</span>
                        <button class="qty-btn" onclick="changeProductQuantity(1)">+</button>
                    </div>
                </div>
            </div>
            
            <div class="details-actions">
                <button class="btn-add-to-cart-details" onclick="addToCartFromDetails()">
                    <i class="fas fa-shopping-bag"></i> أضف إلى السلة
                </button>
                <button class="btn-add-to-cart-details" onclick="addToFavorites()" style="background: linear-gradient(135deg, var(--error), #ef5350);">
                    <i class="fas fa-heart"></i> إضافة للمفضلة
                </button>
            </div>
        </div>
    </div>
</div>

<script>
// EmailJS تهيئة
const EMAILJS_SERVICE_ID = 'service_hlhevor';
const EMAILJS_TEMPLATE_ID = 'template_kqyqfuw';
const EMAILJS_PUBLIC_KEY = 'ZnOxtexlffcGW7r2J';

if (EMAILJS_PUBLIC_KEY && EMAILJS_PUBLIC_KEY !== 'YOUR_PUBLIC_KEY') {
    emailjs.init(EMAILJS_PUBLIC_KEY);
}

// البيانات والمتغيرات العامة
let currentUser = JSON.parse(localStorage.getItem('currentUser')) || null;
let stores = JSON.parse(localStorage.getItem('stores')) || [];
let customers = JSON.parse(localStorage.getItem('customers')) || [];
let adminUsers = JSON.parse(localStorage.getItem('adminUsers')) || [
    { username: 'admin', password: 'admin123', type: 'admin' }
];
let allProducts = JSON.parse(localStorage.getItem('allProducts')) || [];
let cart = JSON.parse(localStorage.getItem('cart')) || [];
let orders = JSON.parse(localStorage.getItem('orders')) || [];
let reviews = JSON.parse(localStorage.getItem('reviews')) || [];
let favorites = JSON.parse(localStorage.getItem('favorites')) || [];

let otpData = JSON.parse(localStorage.getItem('otpData')) || null;
let passwordResetData = JSON.parse(localStorage.getItem('passwordResetData')) || null;
let otpInterval = null;
let resetOtpInterval = null;
let currentProductDetails = null;
let currentProductQuantity = 1;

// دالة عرض الصفحات
function showPage(pageId) {
    const pages = [
        'accountTypePage', 'loginPage', 'storeSignupPage', 'customerSignupPage',
        'adminLoginPage', 'otpPage', 'forgotPasswordPage', 'resetPasswordPage',
        'mainPage', 'customerDashboard', 'storeDashboard', 'adminDashboard'
    ];
    pages.forEach(page => {
        const element = document.getElementById(page);
        if (element) element.classList.add('hidden');
    });
    
    const targetPage = document.getElementById(pageId);
    if (targetPage) targetPage.classList.remove('hidden');
}

// دوال التنقل
function showAccountTypePage() {
    showPage('accountTypePage');
}

function showLoginPage() {
    document.getElementById('loginType').value = '';
    document.getElementById('loginEmail').value = '';
    document.getElementById('loginPass').value = '';
    showPage('loginPage');
}

function showStoreSignup() {
    showPage('storeSignupPage');
}

function showCustomerSignup() {
    showPage('customerSignupPage');
}

function showAdminLogin() {
    showPage('adminLoginPage');
}

function showForgotPasswordPage() {
    document.getElementById('forgotType').value = '';
    document.getElementById('forgotEmail').value = '';
    showPage('forgotPasswordPage');
}

function showHomePage() {
    showMainPage();
}

function showMainPage() {
    updateUI();
    renderStores();
    renderProducts();
    updateCartCount();
    showPage('mainPage');
}

// دوال مساعدة
function showToast(message, type = 'success') {
    const toastContainer = document.getElementById('toastContainer');
    const toast = document.createElement('div');
    toast.className = `toast ${type}`;
    toast.innerHTML = `
        <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'error' ? 'exclamation-circle' : type === 'warning' ? 'exclamation-triangle' : 'info-circle'}"></i>
        <span>${message}</span>
    `;
    toastContainer.appendChild(toast);
    
    setTimeout(() => toast.classList.add('show'), 10);
    setTimeout(() => {
        toast.classList.remove('show');
        setTimeout(() => toast.remove(), 300);
    }, 3000);
}

function validateEmail(email) {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(email);
}

function generateOTP() {
    return Math.floor(100000 + Math.random() * 900000).toString();
}

async function sendOTPEmail(email, otpCode, userName = '', userType = 'customer', isReset = false) {
    try {
        if (!window.emailjs) {
            console.log('OTP Code:', otpCode);
            showToast('رمز التحقق: ' + otpCode, 'info');
            return true;
        }

        const templateParams = {
            email: email,
            user_name: userName,
            otp_code: otpCode,
            expiry_time: '5 دقائق',
            app_name: 'Le Dèlice',
            user_type: userType === 'store' ? 'متجر' : 'عميل',
            is_reset: isReset ? 'نعم' : 'لا'
        };

        await emailjs.send(EMAILJS_SERVICE_ID, EMAILJS_TEMPLATE_ID, templateParams);
        return true;
    } catch (error) {
        console.error('EmailJS Error:', error);
        showToast('رمز التحقق: ' + otpCode, 'info');
        return true;
    }
}

function moveToNext(input, nextIndex) {
    if (input.value.length === 1 && nextIndex < 6) {
        const next = document.querySelector(`.otp-digit[data-index="${nextIndex}"]`);
        if (next) next.focus();
    }
}

function handleOTPInput(event, index) {
    if (event.key === 'Backspace' && !event.target.value && index > 0) {
        const prev = document.querySelector(`.otp-digit[data-index="${index - 1}"]`);
        if (prev) prev.focus();
    }
}

// دوال OTP للتسجيل
function showOTPPage(email, otpCode, userName = '', userData = {}, userType = 'customer') {
    document.getElementById('otpEmail').textContent = email;
    
    otpData = {
        email: email,
        otp: otpCode,
        expiry: Date.now() + 300000,
        userName: userName,
        userData: userData,
        userType: userType
    };
    localStorage.setItem('otpData', JSON.stringify(otpData));
    
    sendOTPEmail(email, otpCode, userName, userType);
    
    const digits = document.querySelectorAll('#otpPage .otp-digit');
    digits.forEach(d => d.value = '');
    
    if (otpInterval) clearInterval(otpInterval);
    otpInterval = setInterval(() => {
        const now = Date.now();
        const remaining = otpData.expiry - now;
        
        if (remaining <= 0) {
            clearInterval(otpInterval);
            document.getElementById('otpTimer').innerHTML = '00:00';
            document.getElementById('verifyOTPBtn').disabled = true;
            return;
        }
        
        const minutes = Math.floor(remaining / 60000);
        const seconds = Math.floor((remaining % 60000) / 1000);
        document.getElementById('otpTimer').innerHTML = 
            `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
    }, 1000);
    
    document.getElementById('resendOTPBtn').disabled = true;
    setTimeout(() => {
        document.getElementById('resendOTPBtn').disabled = false;
    }, 30000);
    
    showPage('otpPage');
}

function verifyOTP() {
    const digits = document.querySelectorAll('#otpPage .otp-digit');
    const enteredOTP = Array.from(digits).map(d => d.value).join('');
    
    if (!otpData) {
        showToast('انتهت صلاحية رمز التحقق', 'error');
        showAccountTypePage();
        return;
    }
    
    if (Date.now() > otpData.expiry) {
        showToast('انتهت صلاحية رمز التحقق', 'error');
        return;
    }
    
    if (enteredOTP.length !== 6) {
        showToast('الرجاء إدخال رمز التحقق كاملاً', 'error');
        return;
    }
    
    if (enteredOTP === otpData.otp) {
        clearInterval(otpInterval);
        
        if (otpData.userType === 'store') {
            const storeData = otpData.userData;
            const storeId = 'store_' + Date.now();
            
            const newStore = {
                id: storeId,
                ownerName: storeData.ownerName,
                storeName: storeData.storeName,
                email: storeData.email,
                phone: storeData.phone,
                password: btoa(storeData.password + "LeDeliceSalt2024"),
                products: [],
                orders: [],
                type: 'store',
                verified: true,
                active: true,
                createdAt: new Date().toISOString()
            };
            
            stores.push(newStore);
            localStorage.setItem('stores', JSON.stringify(stores));
            
            currentUser = {
                id: storeId,
                name: storeData.storeName,
                email: storeData.email,
                type: 'store',
                storeId: storeId
            };
            
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            localStorage.removeItem('otpData');
            otpData = null;
            
            showMainPage();
            showToast('تم تأكيد متجرك بنجاح!', 'success');
            
        } else if (otpData.userType === 'customer') {
            const customerData = otpData.userData;
            const customerId = 'customer_' + Date.now();
            
            const newCustomer = {
                id: customerId,
                name: customerData.name,
                email: customerData.email,
                password: btoa(customerData.password + "LeDeliceSalt2024"),
                type: 'customer',
                verified: true,
                favorites: [],
                createdAt: new Date().toISOString()
            };
            
            customers.push(newCustomer);
            localStorage.setItem('customers', JSON.stringify(customers));
            
            currentUser = {
                id: customerId,
                name: customerData.name,
                email: customerData.email,
                type: 'customer'
            };
            
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            localStorage.removeItem('otpData');
            otpData = null;
            
            showMainPage();
            showToast('تم تأكيد حسابك بنجاح!', 'success');
        }
        
    } else {
        showToast('رمز التحقق غير صحيح', 'error');
    }
}

function resendOTP() {
    if (!otpData) {
        showToast('لا توجد بيانات OTP', 'error');
        showAccountTypePage();
        return;
    }
    
    const newOTP = generateOTP();
    otpData.otp = newOTP;
    otpData.expiry = Date.now() + 300000;
    localStorage.setItem('otpData', JSON.stringify(otpData));
    
    sendOTPEmail(otpData.email, newOTP, otpData.userName, otpData.userType);
    
    if (otpInterval) clearInterval(otpInterval);
    otpInterval = setInterval(() => {
        const now = Date.now();
        const remaining = otpData.expiry - now;
        
        if (remaining <= 0) {
            clearInterval(otpInterval);
            document.getElementById('otpTimer').innerHTML = '00:00';
            document.getElementById('verifyOTPBtn').disabled = true;
            return;
        }
        
        const minutes = Math.floor(remaining / 60000);
        const seconds = Math.floor((remaining % 60000) / 1000);
        document.getElementById('otpTimer').innerHTML = 
            `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
    }, 1000);
    
    document.getElementById('resendOTPBtn').disabled = true;
    setTimeout(() => {
        document.getElementById('resendOTPBtn').disabled = false;
    }, 30000);
    
    showToast('تم إعادة إرسال رمز التحقق', 'success');
}

function goBackFromOTP() {
    if (otpData && otpData.userType === 'store') {
        showStoreSignup();
    } else {
        showCustomerSignup();
    }
}

// دوال التسجيل
function registerStore() {
    const ownerName = document.getElementById('storeOwnerName').value.trim();
    const storeName = document.getElementById('storeName').value.trim();
    const email = document.getElementById('storeEmail').value.trim().toLowerCase();
    const phone = document.getElementById('storePhone').value.trim();
    const password = document.getElementById('storePassword').value;
    const confirmPassword = document.getElementById('storeConfirmPassword').value;

    if (!ownerName || !storeName || !email || !phone || !password || !confirmPassword) {
        showToast('الرجاء إكمال جميع الحقول', 'error');
        return;
    }

    if (!validateEmail(email)) {
        showToast('البريد الإلكتروني غير صالح', 'error');
        return;
    }

    if (password.length < 6) {
        showToast('كلمة المرور يجب أن تكون 6 أحرف على الأقل', 'error');
        return;
    }

    if (password !== confirmPassword) {
        showToast('كلمة المرور غير متطابقة', 'error');
        return;
    }

    const existingStore = stores.find(s => s.email === email);
    if (existingStore) {
        showToast('هذا البريد الإلكتروني مستخدم بالفعل لمتجر آخر', 'error');
        return;
    }

    const userData = {
        ownerName,
        storeName,
        email,
        phone,
        password
    };

    const otp = generateOTP();
    showOTPPage(email, otp, ownerName, userData, 'store');
}

function registerCustomer() {
    const name = document.getElementById('customerName').value.trim();
    const email = document.getElementById('customerEmail').value.trim().toLowerCase();
    const password = document.getElementById('customerPassword').value;
    const confirmPassword = document.getElementById('customerConfirmPassword').value;

    if (!name || !email || !password || !confirmPassword) {
        showToast('الرجاء إكمال جميع الحقول', 'error');
        return;
    }

    if (!validateEmail(email)) {
        showToast('البريد الإلكتروني غير صالح', 'error');
        return;
    }

    if (password.length < 6) {
        showToast('كلمة المرور يجب أن تكون 6 أحرف على الأقل', 'error');
        return;
    }

    if (password !== confirmPassword) {
        showToast('كلمة المرور غير متطابقة', 'error');
        return;
    }

    const existingCustomer = customers.find(c => c.email === email);
    if (existingCustomer) {
        showToast('هذا البريد الإلكتروني مستخدم بالفعل لحساب عميل آخر', 'error');
        return;
    }

    const userData = {
        name,
        email,
        password
    };

    const otp = generateOTP();
    showOTPPage(email, otp, name, userData, 'customer');
}

// دوال تسجيل الدخول
function login() {
    const userType = document.getElementById('loginType').value;
    const email = document.getElementById('loginEmail').value.trim().toLowerCase();
    const password = document.getElementById('loginPass').value;

    if (!userType) {
        showToast('الرجاء اختيار نوع الحساب', 'error');
        return;
    }

    if (!email || !password) {
        showToast('الرجاء إدخال البريد الإلكتروني وكلمة المرور', 'error');
        return;
    }

    if (userType === 'store') {
        const store = stores.find(s => s.email === email && s.password === btoa(password + "LeDeliceSalt2024"));
        if (store) {
            currentUser = {
                id: store.id,
                name: store.storeName,
                email: store.email,
                type: 'store',
                storeId: store.id
            };
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            showMainPage();
            showToast(`مرحباً بك ${store.storeName}`, 'success');
        } else {
            showToast('البريد الإلكتروني أو كلمة المرور غير صحيحة', 'error');
        }
    } else if (userType === 'customer') {
        const customer = customers.find(c => c.email === email && c.password === btoa(password + "LeDeliceSalt2024"));
        if (customer) {
            currentUser = {
                id: customer.id,
                name: customer.name,
                email: customer.email,
                type: 'customer'
            };
            localStorage.setItem('currentUser', JSON.stringify(currentUser));
            showMainPage();
            showToast(`مرحباً بك ${customer.name}`, 'success');
        } else {
            showToast('البريد الإلكتروني أو كلمة المرور غير صحيحة', 'error');
        }
    } else if (userType === 'admin') {
        loginAdmin();
    }
}

function loginAdmin() {
    const username = document.getElementById('adminUsername').value.trim();
    const password = document.getElementById('adminPassword').value;

    if (!username || !password) {
        showToast('الرجاء إدخال اسم المستخدم وكلمة المرور', 'error');
        return;
    }

    const admin = adminUsers.find(a => a.username === username && a.password === password);
    if (admin) {
        currentUser = {
            username: admin.username,
            name: 'مدير النظام',
            type: 'admin'
        };
        localStorage.setItem('currentUser', JSON.stringify(currentUser));
        showMainPage();
        showToast('مرحباً بك في لوحة التحكم', 'success');
    } else {
        showToast('اسم المستخدم أو كلمة المرور غير صحيحة', 'error');
    }
}

function logout() {
    if (confirm('هل تريد تسجيل الخروج؟')) {
        localStorage.removeItem('currentUser');
        currentUser = null;
        showToast('تم تسجيل الخروج بنجاح', 'success');
        setTimeout(() => showAccountTypePage(), 1000);
    }
}

// ----------------- دوال نسيت كلمة المرور المصححة -----------------
function sendPasswordResetOTP() {
    const userType = document.getElementById('forgotType').value;
    const email = document.getElementById('forgotEmail').value.trim().toLowerCase();
    
    if (!userType) {
        showToast('الرجاء اختيار نوع الحساب', 'error');
        return;
    }
    
    if (!email) {
        showToast('الرجاء إدخال البريد الإلكتروني', 'error');
        return;
    }
    
    if (!validateEmail(email)) {
        showToast('البريد الإلكتروني غير صالح', 'error');
        return;
    }
    
    let user = null;
    if (userType === 'customer') {
        user = customers.find(c => c.email === email);
    } else if (userType === 'store') {
        user = stores.find(s => s.email === email);
    }
    
    if (!user) {
        showToast('لا يوجد حساب بهذا البريد الإلكتروني', 'error');
        return;
    }
    
    const otpCode = generateOTP();
    const userName = userType === 'store' ? user.storeName : user.name;
    
    passwordResetData = {
        email: email,
        otp: otpCode,
        expiry: Date.now() + 300000,
        userType: userType,
        userId: user.id,
        userName: userName
    };
    
    localStorage.setItem('passwordResetData', JSON.stringify(passwordResetData));
    
    sendOTPEmail(email, otpCode, userName, userType, true);
    
    document.getElementById('resetEmailText').innerHTML = email;
    
    const digits = document.querySelectorAll('#resetPasswordPage .otp-digit');
    digits.forEach(d => d.value = '');
    
    if (resetOtpInterval) clearInterval(resetOtpInterval);
    
    resetOtpInterval = setInterval(() => {
        const now = Date.now();
        const remaining = passwordResetData.expiry - now;
        
        if (remaining <= 0) {
            clearInterval(resetOtpInterval);
            document.getElementById('resetTimer').innerHTML = '00:00';
            document.getElementById('resetPasswordBtn').disabled = true;
            return;
        }
        
        const minutes = Math.floor(remaining / 60000);
        const seconds = Math.floor((remaining % 60000) / 1000);
        document.getElementById('resetTimer').innerHTML = 
            `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
    }, 1000);
    
    document.getElementById('resendResetOTPBtn').disabled = true;
    setTimeout(() => {
        document.getElementById('resendResetOTPBtn').disabled = false;
    }, 30000);
    
    document.getElementById('resetPasswordBtn').disabled = true;
    
    showPage('resetPasswordPage');
    showToast('تم إرسال رمز التحقق إلى بريدك الإلكتروني', 'success');
}

function resendResetOTP() {
    if (!passwordResetData) {
        showToast('لا توجد بيانات استعادة', 'error');
        showForgotPasswordPage();
        return;
    }
    
    const newOTP = generateOTP();
    passwordResetData.otp = newOTP;
    passwordResetData.expiry = Date.now() + 300000;
    localStorage.setItem('passwordResetData', JSON.stringify(passwordResetData));
    
    sendOTPEmail(passwordResetData.email, newOTP, passwordResetData.userName, passwordResetData.userType, true);
    
    if (resetOtpInterval) clearInterval(resetOtpInterval);
    
    resetOtpInterval = setInterval(() => {
        const now = Date.now();
        const remaining = passwordResetData.expiry - now;
        
        if (remaining <= 0) {
            clearInterval(resetOtpInterval);
            document.getElementById('resetTimer').innerHTML = '00:00';
            document.getElementById('resetPasswordBtn').disabled = true;
            return;
        }
        
        const minutes = Math.floor(remaining / 60000);
        const seconds = Math.floor((remaining % 60000) / 1000);
        document.getElementById('resetTimer').innerHTML = 
            `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
    }, 1000);
    
    document.getElementById('resendResetOTPBtn').disabled = true;
    setTimeout(() => {
        document.getElementById('resendResetOTPBtn').disabled = false;
    }, 30000);
    
    showToast('تم إعادة إرسال رمز التحقق', 'success');
}

function resetPassword() {
    const digits = document.querySelectorAll('#resetPasswordPage .otp-digit');
    const enteredOTP = Array.from(digits).map(d => d.value).join('');
    const newPassword = document.getElementById('newPassword').value;
    const confirmPassword = document.getElementById('confirmNewPassword').value;
    
    if (!passwordResetData) {
        showToast('انتهت صلاحية رمز التحقق', 'error');
        showForgotPasswordPage();
        return;
    }
    
    if (Date.now() > passwordResetData.expiry) {
        showToast('انتهت صلاحية رمز التحقق', 'error');
        return;
    }
    
    if (enteredOTP.length !== 6) {
        showToast('الرجاء إدخال رمز التحقق كاملاً', 'error');
        return;
    }
    
    if (enteredOTP !== passwordResetData.otp) {
        showToast('رمز التحقق غير صحيح', 'error');
        return;
    }
    
    if (!newPassword) {
        showToast('الرجاء إدخال كلمة المرور الجديدة', 'error');
        return;
    }
    
    if (newPassword.length < 6) {
        showToast('كلمة المرور يجب أن تكون 6 أحرف على الأقل', 'error');
        return;
    }
    
    if (newPassword !== confirmPassword) {
        showToast('كلمة المرور غير متطابقة', 'error');
        return;
    }
    
    if (passwordResetData.userType === 'customer') {
        const customerIndex = customers.findIndex(c => c.id === passwordResetData.userId);
        if (customerIndex !== -1) {
            customers[customerIndex].password = btoa(newPassword + "LeDeliceSalt2024");
            localStorage.setItem('customers', JSON.stringify(customers));
            showToast('تم تغيير كلمة المرور بنجاح', 'success');
        }
    } else if (passwordResetData.userType === 'store') {
        const storeIndex = stores.findIndex(s => s.id === passwordResetData.userId);
        if (storeIndex !== -1) {
            stores[storeIndex].password = btoa(newPassword + "LeDeliceSalt2024");
            localStorage.setItem('stores', JSON.stringify(stores));
            showToast('تم تغيير كلمة المرور بنجاح', 'success');
        }
    }
    
    localStorage.removeItem('passwordResetData');
    passwordResetData = null;
    if (resetOtpInterval) clearInterval(resetOtpInterval);
    
    setTimeout(() => showLoginPage(), 1500);
}
// ----------------- نهاية دوال نسيت كلمة المرور -----------------

// دوال UI
function updateUI() {
    const userInfo = document.getElementById('userInfo');
    const userTypeBadge = document.getElementById('userTypeBadge');
    const cartBtn = document.getElementById('cartBtn');
    const adminBtn = document.getElementById('adminBtn');
    const storeBtn = document.getElementById('storeBtn');
    
    if (currentUser) {
        userInfo.textContent = currentUser.name;
        
        userTypeBadge.textContent = currentUser.type === 'store' ? 'متجر' : 
                                   currentUser.type === 'admin' ? 'إدارة' : 'عميل';
        userTypeBadge.className = `user-type-badge ${currentUser.type}`;
        userTypeBadge.classList.remove('hidden');
        
        if (currentUser.type === 'customer') {
            cartBtn.classList.remove('hidden');
        } else {
            cartBtn.classList.add('hidden');
        }
        
        if (currentUser.type === 'admin') {
            adminBtn.classList.remove('hidden');
        } else {
            adminBtn.classList.add('hidden');
        }
        
        if (currentUser.type === 'store') {
            storeBtn.classList.remove('hidden');
        } else {
            storeBtn.classList.add('hidden');
        }
    }
}

// دوال عرض المنتجات والمتاجر
function renderStores() {
    const grid = document.getElementById('storesGrid');
    if (!grid) return;
    
    grid.innerHTML = '';
    
    stores.slice(0, 6).forEach(store => {
        grid.innerHTML += `
            <div class="product-card" onclick="viewStore('${store.id}')">
                <img src="https://images.unsplash.com/photo-1563729784474-d77dbb933a9e?w=400&h=250&fit=crop" class="product-image" alt="${store.storeName}">
                <div class="product-badge">${store.products ? store.products.length : 0} منتج</div>
                <div class="product-content">
                    <h3 class="product-title">${store.storeName}</h3>
                    <p class="product-description">${store.ownerName}</p>
                    <div class="product-actions">
                        <button class="btn-view" onclick="event.stopPropagation(); viewStore('${store.id}')">
                            <i class="fas fa-store"></i> زيارة المتجر
                        </button>
                    </div>
                </div>
            </div>
        `;
    });
}

function renderProducts() {
    const grid = document.getElementById('productsGrid');
    if (!grid) return;
    
    grid.innerHTML = '';
    
    allProducts.slice(0, 8).forEach(product => {
        grid.innerHTML += `
            <div class="product-card" onclick="viewProductDetails('${product.id}')">
                <img src="https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=400&h=250&fit=crop" class="product-image" alt="${product.name}">
                <div class="product-badge">${product.storeName}</div>
                <div class="product-content">
                    <h3 class="product-title">${product.name}</h3>
                    <p class="product-description">${product.description.substring(0, 100)}...</p>
                    <div class="product-price">${product.price} ريال</div>
                    <div class="product-actions">
                        <button class="btn-add-cart" onclick="event.stopPropagation(); addToCart('${product.id}')">
                            <i class="fas fa-shopping-bag"></i> أضف للسلة
                        </button>
                        <button class="btn-view" onclick="event.stopPropagation(); viewProductDetails('${product.id}')">
                            <i class="fas fa-eye"></i> عرض
                        </button>
                    </div>
                </div>
            </div>
        `;
    });
}

function viewStore(storeId) {
    showToast('سيتم عرض منتجات المتجر قريباً', 'info');
}

function viewProductDetails(productId) {
    const product = allProducts.find(p => p.id === productId);
    if (!product) return;
    
    currentProductDetails = product;
    currentProductQuantity = 1;
    
    document.getElementById('detailsTitle').textContent = product.name;
    document.getElementById('detailsStore').innerHTML = `
        <i class="fas fa-store"></i> ${product.storeName}
    `;
    document.getElementById('detailsDescription').textContent = product.description;
    document.getElementById('detailsImage').src = product.image || 'https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=400&h=300&fit=crop';
    document.getElementById('detailsPrice').textContent = `${product.price} ريال`;
    document.getElementById('productQuantity').textContent = currentProductQuantity;
    
    document.getElementById('productDetailsModal').classList.remove('hidden');
}

function closeProductDetails() {
    document.getElementById('productDetailsModal').classList.add('hidden');
}

function changeProductQuantity(change) {
    currentProductQuantity += change;
    if (currentProductQuantity < 1) currentProductQuantity = 1;
    document.getElementById('productQuantity').textContent = currentProductQuantity;
}

function addToCartFromDetails() {
    if (!currentUser || currentUser.type !== 'customer') {
        showToast('يجب تسجيل الدخول كعميل لإضافة المنتجات للسلة', 'error');
        showLoginPage();
        closeProductDetails();
        return;
    }
    
    if (currentProductDetails) {
        addToCart(currentProductDetails.id, currentProductDetails.price, currentProductQuantity);
        closeProductDetails();
    }
}

function addToCart(productId, price, quantity = 1) {
    if (!currentUser || currentUser.type !== 'customer') {
        showToast('يجب تسجيل الدخول كعميل لإضافة المنتجات للسلة', 'error');
        showLoginPage();
        return;
    }
    
    const product = allProducts.find(p => p.id === productId);
    if (!product) return;
    
    let item = cart.find(i => i.productId === productId);
    if (item) { 
        item.qty += quantity; 
    } else { 
        cart.push({ 
            productId, 
            name: product.name,
            storeId: product.storeId,
            storeName: product.storeName,
            price, 
            qty: quantity,
            image: product.image
        }); 
    }
    
    saveCart();
    showToast(`تمت إضافة ${product.name} إلى السلة`, 'success');
}

function saveCart() {
    localStorage.setItem("cart", JSON.stringify(cart));
    updateCartCount();
    if (!document.getElementById('cartModal').classList.contains('hidden')) {
        renderCartItems();
    }
}

function updateCartCount() {
    const count = cart.reduce((total, item) => total + item.qty, 0);
    document.getElementById('cartCount').textContent = count;
}

function toggleCart() {
    const cartModal = document.getElementById('cartModal');
    if (cartModal.classList.contains('hidden')) {
        renderCartItems();
        cartModal.classList.remove('hidden');
    } else {
        cartModal.classList.add('hidden');
    }
}

function renderCartItems() {
    const cartItems = document.getElementById('cartItems');
    const totalAmount = document.getElementById('cartTotalAmount');
    let itemsHTML = '';
    let total = 0;
    
    if (cart.length === 0) {
        itemsHTML = `
            <div class="empty-cart">
                <i class="fas fa-shopping-bag"></i>
                <h3>سلة التسوق فارغة</h3>
                <p>أضف بعض المنتجات لبدء التسوق</p>
            </div>
        `;
    } else {
        cart.forEach((item, index) => {
            const itemTotal = item.price * item.qty;
            total += itemTotal;
            
            itemsHTML += `
                <div class="cart-item">
                    <img src="${item.image || 'https://images.unsplash.com/photo-1578985545062-69928b1d9587?w=100&h=100&fit=crop'}" class="cart-item-image" alt="${item.name}">
                    <div class="cart-item-info">
                        <div class="cart-item-name">${item.name}</div>
                        <div class="cart-item-store">${item.storeName}</div>
                        <div class="cart-item-price">${item.price} × ${item.qty} = ${itemTotal} ريال</div>
                    </div>
                    <div class="cart-item-actions">
                        <div class="quantity-control">
                            <button class="qty-btn" onclick="updateCartItemQuantity(${index}, -1)">-</button>
                            <span class="qty-val">${item.qty}</span>
                            <button class="qty-btn" onclick="updateCartItemQuantity(${index}, 1)">+</button>
                        </div>
                        <button class="remove-item" onclick="removeFromCart(${index})">
                            <i class="fas fa-times"></i>
                        </button>
                    </div>
                </div>
            `;
        });
    }
    
    cartItems.innerHTML = itemsHTML;
    totalAmount.textContent = `${total} ريال`;
}

function updateCartItemQuantity(index, change) {
    cart[index].qty += change;
    if (cart[index].qty < 1) {
        cart.splice(index, 1);
    }
    saveCart();
}

function removeFromCart(index) {
    const itemName = cart[index].name;
    cart.splice(index, 1);
    saveCart();
    showToast(`تم حذف ${itemName} من السلة`, 'success');
}

function clearCart() {
    if (cart.length === 0) return;
    if (confirm("هل أنت متأكد من إفراغ السلة؟")) {
        cart = [];
        saveCart();
        showToast("تم إفراغ السلة", 'success');
        toggleCart();
    }
}

function checkoutWhatsApp() {
    if (cart.length === 0) {
        showToast("السلة فارغة", 'error');
        return;
    }
    
    if (!currentUser) {
        showToast("يجب تسجيل الدخول أولاً", 'error');
        showLoginPage();
        return;
    }
    
    let total = 0;
    let msg = `🚀 طلب جديد من Le Dèlice%0a%0a`;
    msg += `👤 العميل: ${currentUser.name}%0a`;
    msg += `📧 الإيميل: ${currentUser.email}%0a%0a`;
    msg += `🛍️ *المنتجات:*%0a`;
    
    cart.forEach((item, index) => {
        const itemTotal = item.price * item.qty;
        total += itemTotal;
        msg += `${index + 1}. ${item.name}%0a   العدد: ${item.qty}%0a   السعر: ${item.price} ريال%0a   الإجمالي: ${itemTotal} ريال%0a%0a`;
    });
    
    msg += `💰 *الإجمالي الكلي: ${total} ريال*%0a%0a`;
    msg += `⏰ الوقت: ${new Date().toLocaleString('ar-SA')}`;
    
    const phone = "966500000000";
    window.open(`https://wa.me/${phone}?text=${msg}`, '_blank');
    
    showToast('تم فتح واتساب لإرسال الطلب', 'success');
    cart = [];
    saveCart();
    toggleCart();
}

function addToFavorites() {
    showToast('قريباً: إضافة للمفضلة', 'info');
}

function showStoreDashboard() {
    showToast('لوحة تحكم المتجر قريباً', 'info');
}

function showAdminDashboard() {
    showToast('لوحة تحكم الإدارة قريباً', 'info');
}

function viewStoreOrders() {
    showToast('الطلبات قريباً', 'info');
}

function processOrders() {
    showToast('معالجة الطلبات قريباً', 'info');
}

function viewStoreAnalytics() {
    showToast('التقارير قريباً', 'info');
}

function changeStorePassword() {
    showToast('تغيير كلمة المرور قريباً', 'info');
}

function storeSettings() {
    showToast('الإعدادات قريباً', 'info');
}

function storeSocialMedia() {
    showToast('روابط التواصل قريباً', 'info');
}

function pauseStore() {
    showToast('إيقاف المتجر قريباً', 'info');
}

function deleteStoreAccount() {
    showToast('حذف المتجر قريباً', 'info');
}

function exportStoreData() {
    showToast('تصدير البيانات قريباً', 'info');
}

function manageStoreProducts() {
    showToast('إدارة المنتجات قريباً', 'info');
}

function addNewProduct() {
    showToast('إضافة منتج قريباً', 'info');
}

function editStoreProduct(productId) {
    showToast('تعديل المنتج قريباً', 'info');
}

function deleteStoreProduct(productId) {
    showToast('حذف المنتج قريباً', 'info');
}

function manageAllStores() {
    showToast('إدارة المتاجر قريباً', 'info');
}

function addNewStore() {
    showToast('إضافة متجر قريباً', 'info');
}

function manageAllCustomers() {
    showToast('إدارة العملاء قريباً', 'info');
}

function viewCustomerReports() {
    showToast('تقارير العملاء قريباً', 'info');
}

function manageAllProducts() {
    showToast('إدارة المنتجات قريباً', 'info');
}

function productAnalytics() {
    showToast('تحليل المنتجات قريباً', 'info');
}

function manageAllOrders() {
    showToast('إدارة الطلبات قريباً', 'info');
}

function salesReports() {
    showToast('تقارير المبيعات قريباً', 'info');
}

function systemSettings() {
    showToast('إعدادات النظام قريباً', 'info');
}

function backupSystem() {
    showToast('النسخ الاحتياطي قريباً', 'info');
}

function maintenanceMode() {
    showToast('وضع الصيانة قريباً', 'info');
}

function viewActivityLog() {
    showToast('سجل النشاطات قريباً', 'info');
}

function manageAdmins() {
    showToast('إدارة المشرفين قريباً', 'info');
}

function clearAllData() {
    if (confirm('⚠️ تحذير: هل أنت متأكد من حذف جميع البيانات؟')) {
        showToast('تم حذف جميع البيانات', 'success');
    }
}

function filterProducts() {
    const term = document.getElementById("searchInput").value.toLowerCase();
    if (term) {
        showToast(`بحث عن: ${term}`, 'info');
    }
}

// تهيئة الصفحة
window.addEventListener('load', function() {
    // تحميل البيانات المحفوظة
    const savedOTPData = localStorage.getItem("otpData");
    if (savedOTPData) {
        otpData = JSON.parse(savedOTPData);
        if (Date.now() > otpData.expiry) {
            localStorage.removeItem("otpData");
            otpData = null;
        }
    }
    
    const savedResetData = localStorage.getItem("passwordResetData");
    if (savedResetData) {
        passwordResetData = JSON.parse(savedResetData);
        if (Date.now() > passwordResetData.expiry) {
            localStorage.removeItem("passwordResetData");
            passwordResetData = null;
        }
    }
    
    // بيانات تجريبية
    if (stores.length === 0) {
        stores.push({
            id: 'store_demo',
            ownerName: 'أحمد محمد',
            storeName: 'حلويات الجنة',
            email: 'store@example.com',
            phone: '966500000001',
            password: btoa('store123' + "LeDeliceSalt2024"),
            products: [],
            type: 'store',
            verified: true,
            active: true,
            createdAt: new Date().toISOString()
        });
        localStorage.setItem('stores', JSON.stringify(stores));
    }
    
    if (customers.length === 0) {
        customers.push({
            id: 'customer_demo',
            name: 'خالد سعيد',
            email: 'customer@example.com',
            password: btoa('customer123' + "LeDeliceSalt2024"),
            type: 'customer',
            verified: true,
            favorites: [],
            createdAt: new Date().toISOString()
        });
        localStorage.setItem('customers', JSON.stringify(customers));
    }
    
    if (allProducts.length === 0) {
        allProducts.push(
            {
                id: 'product_1',
                storeId: 'store_demo',
                storeName: 'حلويات الجنة',
                name: 'كيك الشوكولاتة الفاخر',
                description: 'كيك شوكولاتة بلجيكي مع طبقة غنية من الكريمة',
                price: 85,
                category: 'كيك',
                image: '',
                createdAt: new Date().toISOString()
            },
            {
                id: 'product_2',
                storeId: 'store_demo',
                storeName: 'حلويات الجنة',
                name: 'معمول التمر',
                description: 'معمول منزلي بتمر العنبرة مع مكسرات',
                price: 45,
                category: 'معمول',
                image: '',
                createdAt: new Date().toISOString()
            }
        );
        localStorage.setItem('allProducts', JSON.stringify(allProducts));
    }
    
    if (currentUser) {
        showMainPage();
    } else {
        showAccountTypePage();
    }
});
</script>
</body>
</html>
