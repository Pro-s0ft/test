<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام مبيعات السيراميك - Ceramic Sales Pro</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #d4a574;
            --secondary: #2a2a2a;
            --accent: #e8d4c4;
            --success: #4ecdc4;
            --danger: #ff6b6b;
            --light-bg: #faf8f6;
            --border: #e0d5ce;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, var(--light-bg) 0%, #f5ede4 100%);
            color: var(--secondary);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        /* Header */
        .header {
            text-align: center;
            margin-bottom: 40px;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .header h1 {
            font-size: 2.5em;
            color: var(--secondary);
            margin-bottom: 10px;
            font-weight: 700;
            letter-spacing: -1px;
        }

        .header p {
            color: #666;
            font-size: 1.1em;
        }

        /* Main Grid */
        .main-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-bottom: 30px;
        }

        @media (max-width: 1024px) {
            .main-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Cards */
        .card {
            background: white;
            border-radius: 16px;
            padding: 30px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
            border: 1px solid var(--border);
            animation: fadeIn 0.6s ease-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .card h2 {
            color: var(--secondary);
            margin-bottom: 25px;
            font-size: 1.5em;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .card h2::before {
            content: '';
            width: 4px;
            height: 24px;
            background: var(--primary);
            border-radius: 2px;
        }

        /* Form Group */
        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: var(--secondary);
            font-weight: 600;
            font-size: 0.95em;
        }

        input, select {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid var(--border);
            border-radius: 8px;
            font-size: 1em;
            transition: all 0.3s ease;
            font-family: inherit;
        }

        input:focus, select:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(212, 165, 116, 0.1);
        }

        input::placeholder {
            color: #999;
        }

        /* Buttons */
        .button {
            padding: 12px 24px;
            border: none;
            border-radius: 8px;
            font-size: 1em;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .btn-primary {
            background: var(--primary);
            color: white;
            width: 100%;
            margin-top: 10px;
        }

        .btn-primary:hover {
            background: #c49463;
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(212, 165, 116, 0.3);
        }

        .btn-secondary {
            background: var(--success);
            color: white;
            flex: 1;
        }

        .btn-secondary:hover {
            background: #3bb5b0;
            transform: translateY(-2px);
        }

        .btn-danger {
            background: var(--danger);
            color: white;
            flex: 1;
            margin-right: 10px;
        }

        .btn-danger:hover {
            background: #ff5252;
            transform: translateY(-2px);
        }

        /* Price Display */
        .price-display {
            background: linear-gradient(135deg, var(--accent) 0%, rgba(232, 212, 196, 0.5) 100%);
            padding: 20px;
            border-radius: 12px;
            margin-top: 20px;
            text-align: center;
            border: 2px solid var(--primary);
        }

        .price-display p {
            color: #666;
            margin-bottom: 8px;
            font-size: 0.95em;
        }

        .price-display .price {
            font-size: 2.5em;
            color: var(--primary);
            font-weight: 700;
        }

        .price-display .unit {
            font-size: 0.9em;
            color: var(--secondary);
            margin-right: 5px;
        }

        /* Pricing Settings */
        .pricing-section {
            background: linear-gradient(135deg, #fff9f5 0%, #fef5f0 100%);
            padding: 20px;
            border-radius: 12px;
            margin-bottom: 20px;
            border: 1px solid var(--border);
        }

        .pricing-section h3 {
            color: var(--secondary);
            margin-bottom: 15px;
            font-size: 1.1em;
        }

        .price-input-group {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        /* Products Table */
        .products-section {
            grid-column: 1 / -1;
        }

        .table-wrapper {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th {
            background: var(--secondary);
            color: white;
            padding: 15px;
            text-align: right;
            font-weight: 600;
        }

        td {
            padding: 15px;
            border-bottom: 1px solid var(--border);
        }

        tr:hover {
            background: var(--light-bg);
        }

        .action-buttons {
            display: flex;
            gap: 10px;
        }

        .btn-small {
            padding: 6px 12px;
            font-size: 0.85em;
            border-radius: 6px;
            border: none;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .btn-edit {
            background: #3498db;
            color: white;
        }

        .btn-edit:hover {
            background: #2980b9;
        }

        .btn-delete {
            background: var(--danger);
            color: white;
        }

        .btn-delete:hover {
            background: #ff5252;
        }

        /* Summary */
        .summary {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .summary-card {
            background: white;
            padding: 20px;
            border-radius: 12px;
            border-left: 4px solid var(--primary);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }

        .summary-card h3 {
            color: #666;
            font-size: 0.9em;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .summary-card .value {
            font-size: 1.8em;
            color: var(--secondary);
            font-weight: 700;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            animation: fadeIn 0.3s ease-out;
        }

        .modal.active {
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 16px;
            width: 90%;
            max-width: 500px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
        }

        .modal-content h3 {
            margin-bottom: 20px;
            color: var(--secondary);
        }

        /* Print Styles */
        @media print {
            body {
                background: white;
            }
            .btn-primary, .action-buttons, .header {
                display: none;
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 1.8em;
            }

            .main-grid {
                gap: 20px;
            }

            .card {
                padding: 20px;
            }

            .price-input-group {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🏛️ نظام مبيعات السيراميك</h1>
            <p>إدارة الطلبات وحساب الأسعار بكل سهولة</p>
            <a href="ceramic_menu.html" style="margin-top: 15px; display: inline-block; padding: 10px 20px; background: var(--success); color: white; border-radius: 8px; text-decoration: none; font-weight: 600; transition: all 0.3s ease;" onmouseover="this.style.background='#3bb5b0'" onmouseout="this.style.background='var(--success)'">← العودة للقائمة الرئيسية</a>
        </div>

        <div class="main-grid">
            <!-- Left: Settings & Add Product -->
            <div>
                <div class="card">
                    <h2>إعدادات التسعير</h2>
                    <div class="pricing-section">
                        <h3>💰 السعر الأساسي (للمتر المربع)</h3>
                        <div class="form-group">
                            <label>السعر لكل متر مربع (بالجنيه)</label>
                            <input type="number" id="pricePerSqMeter" value="100" min="0" step="0.01">
                        </div>
                    </div>

                    <div class="pricing-section">
                        <h3>📋 بيانات المنتج</h3>
                        <div class="form-group">
                            <label>اسم المنتج</label>
                            <input type="text" id="productName" placeholder="مثال: سيراميك جدران - فاخر">
                        </div>

                        <div class="form-group">
                            <label>وحدة القياس</label>
                            <select id="unitSelect" onchange="updateUnitLabel()">
                                <option value="cm">سنتيمتر (سم)</option>
                                <option value="m">متر (م)</option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label>الطول (<span id="lengthUnit">سم</span>)</label>
                            <input type="number" id="length" placeholder="أدخل الطول" min="1" step="0.1">
                        </div>

                        <div class="form-group">
                            <label>العرض (<span id="widthUnit">سم</span>)</label>
                            <input type="number" id="width" placeholder="أدخل العرض" min="1" step="0.1">
                        </div>

                        <div class="form-group">
                            <label>الكمية</label>
                            <input type="number" id="quantity" value="1" min="1" step="1">
                        </div>

                        <div class="price-display">
                            <p>سعر الوحدة الواحدة</p>
                            <div>
                                <span class="unit">جنيه</span>
                                <span class="price" id="unitPrice">0.00</span>
                            </div>
                        </div>

                        <button class="button btn-primary" onclick="addProduct()">✏️ إضافة المنتج</button>
                    </div>
                </div>
            </div>

            <!-- Right: Order Summary -->
            <div>
                <div class="card">
                    <h2>ملخص الطلب</h2>
                    <div id="summaryContainer"></div>
                </div>
            </div>
        </div>

        <!-- Products List -->
        <div class="card products-section">
            <h2>قائمة المنتجات في الطلب</h2>
            <div class="table-wrapper">
                <table id="productsTable">
                    <thead>
                        <tr>
                            <th>المنتج</th>
                            <th>الأبعاد</th>
                            <th>المساحة (م²)</th>
                            <th>الكمية</th>
                            <th>سعر الوحدة</th>
                            <th>الإجمالي</th>
                            <th>الإجراءات</th>
                        </tr>
                    </thead>
                    <tbody id="tableBody">
                    </tbody>
                </table>
            </div>
            <div style="margin-top: 20px; display: flex; gap: 10px; flex-wrap: wrap;">
                <button class="button btn-secondary" onclick="printOrder()">🖨️ طباعة</button>
                <button class="button btn-secondary" onclick="saveOrder()">💾 حفظ الطلب</button>
                <button class="button btn-secondary" onclick="clearAll()">🔄 مسح الكل</button>
                <button class="button btn-secondary" onclick="exportToCSV()">📥 تصدير CSV</button>
            </div>
        </div>
    </div>

    <script src="shared-state.js"></script>
    <script>
        let products = [];
        let currentUnit = 'cm'; // المتغير العام لوحدة القياس

        // تحميل البيانات عند فتح الصفحة
        window.addEventListener('DOMContentLoaded', function() {
            loadSavedProducts();
            loadDefaultPrice();
        });

        // تحديث السعر عند تغيير القيم
        document.getElementById('length').addEventListener('input', updateUnitPrice);
        document.getElementById('width').addEventListener('input', updateUnitPrice);
        document.getElementById('pricePerSqMeter').addEventListener('input', updateUnitPrice);

        // دالة تحميل المنتجات المحفوظة
        function loadSavedProducts() {
            products = appState.getCart();
            if (products.length > 0) {
                renderTable();
                updateSummary();
            }
        }

        // تحميل السعر الافتراضي من الإعدادات
        function loadDefaultPrice() {
            const settings = JSON.parse(localStorage.getItem('ceramicSettings') || '{}');
            if (settings.defaultPrice) {
                document.getElementById('pricePerSqMeter').value = settings.defaultPrice;
            }
        }

        // دالة تحديث وحدة القياس
        function updateUnitLabel() {
            currentUnit = document.getElementById('unitSelect').value;
            const lengthUnit = document.getElementById('lengthUnit');
            const widthUnit = document.getElementById('widthUnit');
            
            if (currentUnit === 'cm') {
                lengthUnit.textContent = 'سم';
                widthUnit.textContent = 'سم';
            } else {
                lengthUnit.textContent = 'م';
                widthUnit.textContent = 'م';
            }
            
            // إعادة حساب السعر عند تغيير الوحدة
            updateUnitPrice();
        }

        function updateUnitPrice() {
            const length = parseFloat(document.getElementById('length').value) || 0;
            const width = parseFloat(document.getElementById('width').value) || 0;
            const pricePerSqMeter = parseFloat(document.getElementById('pricePerSqMeter').value) || 0;

            let lengthInMeters, widthInMeters;

            // تحويل بناءً على الوحدة المختارة
            if (currentUnit === 'cm') {
                lengthInMeters = length / 100;
                widthInMeters = width / 100;
            } else {
                lengthInMeters = length;
                widthInMeters = width;
            }

            const areaInSqMeters = lengthInMeters * widthInMeters;
            const unitPrice = areaInSqMeters * pricePerSqMeter;
            document.getElementById('unitPrice').textContent = unitPrice.toFixed(2);
        }

        function addProduct() {
            const name = document.getElementById('productName').value.trim();
            const length = parseFloat(document.getElementById('length').value);
            const width = parseFloat(document.getElementById('width').value);
            const quantity = parseInt(document.getElementById('quantity').value);
            const pricePerSqMeter = parseFloat(document.getElementById('pricePerSqMeter').value);

            if (!name) {
                alert('الرجاء إدخال اسم المنتج');
                return;
            }

            if (!length || !width || length <= 0 || width <= 0) {
                alert('الرجاء إدخال أبعاد صحيحة');
                return;
            }

            if (quantity <= 0) {
                alert('الرجاء إدخال كمية صحيحة');
                return;
            }

            // تحويل إلى متر بناءً على الوحدة المختارة
            let lengthInMeters, widthInMeters;
            
            if (currentUnit === 'cm') {
                lengthInMeters = length / 100;
                widthInMeters = width / 100;
            } else {
                lengthInMeters = length;
                widthInMeters = width;
            }

            const areaPerUnit = lengthInMeters * widthInMeters;
            const unitPrice = areaPerUnit * pricePerSqMeter;
            const totalPrice = unitPrice * quantity;

            const product = {
                id: Date.now(),
                name,
                length,
                width,
                unit: currentUnit,
                quantity,
                areaPerUnit,
                unitPrice,
                totalPrice,
                pricePerSqMeter
            };

            appState.addToCart(product);
            products.push(product);
            renderTable();
            updateSummary();
            resetForm();
        }

        function deleteProduct(id) {
            appState.removeFromCart(id);
            products = products.filter(p => p.id !== id);
            renderTable();
            updateSummary();
        }

        function renderTable() {
            const tbody = document.getElementById('tableBody');
            tbody.innerHTML = '';

            products.forEach(product => {
                const unitLabel = product.unit === 'cm' ? 'سم' : 'م';
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td><strong>${product.name}</strong></td>
                    <td>${product.length} × ${product.width} ${unitLabel}</td>
                    <td>${product.areaPerUnit.toFixed(4)}</td>
                    <td>${product.quantity}</td>
                    <td>${product.unitPrice.toFixed(2)} جنيه</td>
                    <td><strong>${product.totalPrice.toFixed(2)} جنيه</strong></td>
                    <td>
                        <div class="action-buttons">
                            <button class="btn-small btn-delete" onclick="deleteProduct(${product.id})">حذف</button>
                        </div>
                    </td>
                `;
                tbody.appendChild(row);
            });
        }

        function updateSummary() {
            const totalItems = products.reduce((sum, p) => sum + p.quantity, 0);
            const totalArea = products.reduce((sum, p) => sum + (p.areaPerUnit * p.quantity), 0);
            const totalPrice = products.reduce((sum, p) => sum + p.totalPrice, 0);

            const summaryHTML = `
                <div class="summary">
                    <div class="summary-card">
                        <h3>📦 إجمالي العناصر</h3>
                        <div class="value">${totalItems}</div>
                    </div>
                    <div class="summary-card">
                        <h3>📐 إجمالي المساحة</h3>
                        <div class="value">${totalArea.toFixed(2)}</div>
                        <p style="font-size: 0.8em; color: #999; margin-top: 5px;">متر مربع</p>
                    </div>
                    <div class="summary-card">
                        <h3>💵 الإجمالي</h3>
                        <div class="value" style="color: var(--primary);">${totalPrice.toFixed(2)}</div>
                        <p style="font-size: 0.8em; color: #999; margin-top: 5px;">جنيه</p>
                    </div>
                </div>
            `;

            document.getElementById('summaryContainer').innerHTML = summaryHTML;
        }

        function resetForm() {
            document.getElementById('productName').value = '';
            document.getElementById('length').value = '';
            document.getElementById('width').value = '';
            document.getElementById('quantity').value = '1';
            updateUnitPrice();
        }

        function clearAll() {
            if (confirm('هل تريد مسح جميع المنتجات؟')) {
                appState.clearCart();
                products = [];
                renderTable();
                updateSummary();
            }
        }

        function saveOrder() {
            const totalPrice = products.reduce((sum, p) => sum + p.totalPrice, 0);
            const totalArea = products.reduce((sum, p) => sum + (p.areaPerUnit * p.quantity), 0);
            
            const order = {
                id: Date.now(),
                products: products,
                totalPrice: totalPrice,
                totalArea: totalArea,
                totalItems: products.reduce((sum, p) => sum + p.quantity, 0),
                timestamp: new Date().toLocaleString('ar-EG')
            };

            appState.addOrder(order);
            alert('✅ تم حفظ الطلب بنجاح!');
        }

        function printOrder() {
            window.print();
        }

        function exportToCSV() {
            let csv = 'المنتج,الطول,العرض,الوحدة,المساحة (م²),الكمية,سعر الوحدة,الإجمالي\n';
            
            products.forEach(p => {
                const unitLabel = p.unit === 'cm' ? 'سم' : 'م';
                csv += `"${p.name}",${p.length},${p.width},${unitLabel},${p.areaPerUnit.toFixed(4)},${p.quantity},${p.unitPrice.toFixed(2)},${p.totalPrice.toFixed(2)}\n`;
            });

            const totalPrice = products.reduce((sum, p) => sum + p.totalPrice, 0);
            csv += `\n,,,,,الإجمالي:,${totalPrice.toFixed(2)}\n`;

            const blob = new Blob([csv], { type: 'text/csv;charset=utf-8;' });
            const link = document.createElement('a');
            link.href = URL.createObjectURL(blob);
            link.download = `ceramic-sales-${new Date().toLocaleDateString('ar-EG')}.csv`;
            link.click();
        }

        // تحديث السعر في البداية
        updateUnitPrice();
        updateSummary();
    </script>
</body>
</html>
