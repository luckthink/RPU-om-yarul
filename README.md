<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rpu Om Yarul - Buat Pesanan Anda</title>
    <script src="https://cdn.tailwindcss.com/3.3.0"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        
        body { 
            font-family: 'Inter', sans-serif; 
        }
        
        .chicken-pattern {
            background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23f97316' fill-opacity='0.05'%3E%3Cpath d='M30 30c0-11.046-8.954-20-20-20s-20 8.954-20 20 8.954 20 20 20 20-8.954 20-20zm0 0c0-11.046 8.954-20 20-20s20 8.954 20 20-8.954 20-20 20-20-8.954-20-20z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
        }

        /* Custom utility classes for better production compatibility */
        .btn-primary {
            background: linear-gradient(135deg, #10b981, #059669);
            color: white;
            padding: 1rem 1.5rem;
            border-radius: 0.75rem;
            font-weight: 600;
            font-size: 1.125rem;
            transition: all 0.2s;
            transform: scale(1);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            width: 100%;
        }

        .btn-primary:hover {
            background: linear-gradient(135deg, #059669, #047857);
            transform: scale(1.05);
        }

        .btn-disabled {
            background-color: #d1d5db;
            color: #6b7280;
            padding: 1rem 1.5rem;
            border-radius: 0.75rem;
            font-weight: 600;
            font-size: 1.125rem;
            cursor: not-allowed;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            width: 100%;
        }

        .menu-card {
            background: white;
            border-radius: 1rem;
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            transition: all 0.3s;
            transform: translateY(0);
        }

        .menu-card:hover {
            box-shadow: 0 25px 25px -5px rgba(0, 0, 0, 0.1);
            transform: translateY(-4px);
        }

        .order-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            background-color: #f9fafb;
            padding: 0.75rem;
            border-radius: 0.5rem;
        }

        .quantity-btn {
            width: 2rem;
            height: 2rem;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s;
        }

        .quantity-btn-minus {
            background-color: #fee2e2;
            color: #dc2626;
        }

        .quantity-btn-minus:hover {
            background-color: #fecaca;
        }

        .quantity-btn-plus {
            background-color: #dcfce7;
            color: #16a34a;
        }

        .quantity-btn-plus:hover {
            background-color: #bbf7d0;
        }
    </style>
</head>
<body class="bg-gradient-to-br from-orange-50 to-red-50 chicken-pattern min-h-screen">
    <div class="container mx-auto px-4 py-8 max-w-6xl">
        <!-- Header -->
        <div class="text-center mb-12">
            <div class="inline-flex items-center justify-center w-20 h-20 bg-gradient-to-br from-orange-500 to-red-500 rounded-full mb-6 shadow-lg">
                <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.94-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/>
                </svg>
            </div>
            <h1 class="text-4xl font-bold text-gray-800 mb-2">Rpu Om Yarul</h1>
            <p class="text-xl text-gray-600 font-medium">Buat Sendiri Pesanan Anda</p>
            <div class="w-24 h-1 bg-gradient-to-r from-orange-500 to-red-500 mx-auto mt-4 rounded-full"></div>
        </div>

        <!-- Menu Items -->
        <div class="mb-12">
            <h2 class="text-2xl font-semibold text-gray-800 mb-6 flex items-center">
                <span class="w-8 h-8 bg-orange-500 rounded-full flex items-center justify-center text-white font-bold text-sm mr-3">1</span>
                Pilih Menu Favorit Anda
            </h2>
            
            <div class="grid md:grid-cols-3 gap-6">
                <!-- Ayam Merah -->
                <div class="menu-card">
                    <div class="h-48 bg-gradient-to-br from-red-400 to-red-600 flex items-center justify-center">
                        <svg class="w-24 h-24 text-white opacity-90" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M8.5 5c-1.5 0-2.5 1-2.5 2.5S7 10 8.5 10s2.5-1 2.5-2.5S10 5 8.5 5zM12 2c-1.1 0-2 .9-2 2s.9 2 2 2 2-.9 2-2-.9-2-2-2zm7 9c0-3.87-3.13-7-7-7S5 7.13 5 11c0 1.19.3 2.3.82 3.28L8 18h8l2.18-3.72c.52-.98.82-2.09.82-3.28z"/>
                        </svg>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold text-gray-800 mb-4">Ayam Merah</h3>
                        <div class="flex items-center justify-between">
                            <span class="text-2xl font-bold text-red-600">Rp 55.000</span>
                            <button onclick="addItem('Ayam Merah', 55000)" class="bg-red-500 hover:bg-red-600 text-white px-6 py-2 rounded-full font-medium transition-colors duration-200">
                                Tambah
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Daging -->
                <div class="menu-card">
                    <div class="h-48 bg-gradient-to-br from-amber-400 to-orange-600 flex items-center justify-center">
                        <svg class="w-24 h-24 text-white opacity-90" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                        </svg>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold text-gray-800 mb-4">Daging</h3>
                        <div class="flex items-center justify-between">
                            <span class="text-2xl font-bold text-orange-600">Rp 30.000</span>
                            <button onclick="addItem('Daging', 30000)" class="bg-orange-500 hover:bg-orange-600 text-white px-6 py-2 rounded-full font-medium transition-colors duration-200">
                                Tambah
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Glondingan -->
                <div class="menu-card">
                    <div class="h-48 bg-gradient-to-br from-green-400 to-emerald-600 flex items-center justify-center">
                        <svg class="w-24 h-24 text-white opacity-90" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8zm-5.5-2.5l7.51-3.49L17.5 6.5 9.99 9.99 6.5 17.5zm5.5-6.6c.61 0 1.1.49 1.1 1.1s-.49 1.1-1.1 1.1-1.1-.49-1.1-1.1.49-1.1 1.1-1.1z"/>
                        </svg>
                    </div>
                    <div class="p-6">
                        <h3 class="text-xl font-semibold text-gray-800 mb-4">Glondongan</h3>
                        <div class="flex items-center justify-between">
                            <span class="text-2xl font-bold text-emerald-600">Rp 28.000</span>
                            <button onclick="addItem('Glondongan', 28000)" class="bg-emerald-500 hover:bg-emerald-600 text-white px-6 py-2 rounded-full font-medium transition-colors duration-200">
                                Tambah
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Order Summary -->
        <div class="max-w-2xl mx-auto">
            <div class="bg-white rounded-2xl shadow-lg p-6">
                <h3 class="text-xl font-semibold text-gray-800 mb-2 flex items-center">
                    <span class="w-8 h-8 bg-orange-500 rounded-full flex items-center justify-center text-white font-bold text-sm mr-3">2</span>
                    Pesanan Anda
                </h3>
                <p class="text-sm text-gray-600 mb-4">Cek kembali sebelum dipesan</p>
                
                <div id="orderItems" class="space-y-3 mb-6 min-h-[100px]">
                    <div class="text-center text-gray-500 py-8">
                        <svg class="w-12 h-12 mx-auto mb-3 opacity-50" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M7 4V2C7 1.45 7.45 1 8 1H16C16.55 1 17 1.45 17 2V4H20C20.55 4 21 4.45 21 5S20.55 6 20 6H19V19C19 20.1 18.1 21 17 21H7C5.9 21 5 20.1 5 19V6H4C3.45 6 3 5.55 3 5S3.45 4 4 4H7ZM9 3V4H15V3H9ZM7 6V19H17V6H7Z"/>
                        </svg>
                        <p>Belum ada item dipilih</p>
                    </div>
                </div>
                
                <div class="border-t pt-4">
                    <div class="flex justify-between items-center mb-4">
                        <span class="text-lg font-semibold text-gray-800">Total:</span>
                        <span id="totalPrice" class="text-2xl font-bold text-orange-600">Rp 0</span>
                    </div>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-3">
                        <button id="orderButton1" onclick="placeOrder('6285640044378')" disabled class="w-full bg-gray-300 text-gray-500 py-4 rounded-xl font-semibold text-lg transition-all duration-200 cursor-not-allowed flex items-center justify-center space-x-2">
                            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.890-5.335 11.893-11.893A11.821 11.821 0 0020.465 3.516"/>
                            </svg>
                            <span>WA Yarul</span>
                        </button>
                        <button id="orderButton2" onclick="placeOrder('6287796982839')" disabled class="w-full bg-gray-300 text-gray-500 py-4 rounded-xl font-semibold text-lg transition-all duration-200 cursor-not-allowed flex items-center justify-center space-x-2">
                            <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.890-5.335 11.893-11.893A11.821 11.821 0 0020.465 3.516"/>
                            </svg>
                            <span>WA Nisa</span>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        let orderItems = [];
        let total = 0;

        function addItem(name, price) {
            const existingItem = orderItems.find(item => item.name === name);
            
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                orderItems.push({ name, price, quantity: 1 });
            }
            
            updateOrderDisplay();
        }

        function removeItem(name) {
            const itemIndex = orderItems.findIndex(item => item.name === name);
            if (itemIndex > -1) {
                if (orderItems[itemIndex].quantity > 1) {
                    orderItems[itemIndex].quantity -= 1;
                } else {
                    orderItems.splice(itemIndex, 1);
                }
            }
            updateOrderDisplay();
        }

        function updateOrderDisplay() {
            const orderItemsDiv = document.getElementById('orderItems');
            const totalPriceSpan = document.getElementById('totalPrice');
            const orderButton1 = document.getElementById('orderButton1');
            const orderButton2 = document.getElementById('orderButton2');
            
            if (orderItems.length === 0) {
                orderItemsDiv.innerHTML = `
                    <div class="text-center text-gray-500 py-8">
                        <svg class="w-12 h-12 mx-auto mb-3 opacity-50" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M7 4V2C7 1.45 7.45 1 8 1H16C16.55 1 17 1.45 17 2V4H20C20.55 4 21 4.45 21 5S20.55 6 20 6H19V19C19 20.1 18.1 21 17 21H7C5.9 21 5 20.1 5 19V6H4C3.45 6 3 5.55 3 5S3.45 4 4 4H7ZM9 3V4H15V3H9ZM7 6V19H17V6H7Z"/>
                        </svg>
                        <p>Belum ada item dipilih</p>
                    </div>
                `;
                total = 0;
                orderButton1.disabled = true;
                orderButton2.disabled = true;
                orderButton1.className = "btn-disabled";
                orderButton2.className = "btn-disabled";
            } else {
                orderItemsDiv.innerHTML = orderItems.map(item => `
                    <div class="order-item">
                        <div class="flex-1">
                            <h4 class="font-medium text-gray-800">${item.name}</h4>
                            <p class="text-sm text-gray-600">Rp ${item.price.toLocaleString('id-ID')} x ${item.quantity}</p>
                        </div>
                        <div class="flex items-center space-x-2">
                            <button onclick="removeItem('${item.name}')" class="quantity-btn quantity-btn-minus">
                                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M19 13H5v-2h14v2z"/>
                                </svg>
                            </button>
                            <span class="w-8 text-center font-medium">${item.quantity}</span>
                            <button onclick="addItem('${item.name}', ${item.price})" class="quantity-btn quantity-btn-plus">
                                <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
                                    <path d="M19 13h-6v6h-2v-6H5v-2h6V5h2v6h6v2z"/>
                                </svg>
                            </button>
                        </div>
                    </div>
                `).join('');
                
                total = orderItems.reduce((sum, item) => sum + (item.price * item.quantity), 0);
                orderButton1.disabled = false;
                orderButton2.disabled = false;
                orderButton1.className = "btn-primary";
                orderButton2.className = "btn-primary";
            }
            
            totalPriceSpan.textContent = `Rp ${total.toLocaleString('id-ID')}`;
        }

        function placeOrder(whatsappNumber) {
            if (orderItems.length === 0) return;
            
            const orderSummary = orderItems.map(item => 
                `${item.name} x${item.quantity} - Rp ${(item.price * item.quantity).toLocaleString('id-ID')}`
            ).join('%0A');
            
            // Create WhatsApp message with proper encoding
            const whatsappMessage = `Halo Rpu Om Yarul! 🍗%0A%0ASaya ingin memesan:%0A%0A${orderSummary}%0A%0A*Total: Rp ${total.toLocaleString('id-ID')}*%0A%0AMohon konfirmasi pesanan saya. Terima kasih!`;
            
            // Create WhatsApp URL
            const whatsappURL = `https://wa.me/${whatsappNumber}?text=${whatsappMessage}`;
            
            // Open WhatsApp
            window.open(whatsappURL, '_blank');
            
            // Reset order after sending to WhatsApp
            setTimeout(() => {
                orderItems = [];
                updateOrderDisplay();
            }, 1000);
        }
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'970a1a4cd64efda7',t:'MTc1NTQ0MzQ3My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
