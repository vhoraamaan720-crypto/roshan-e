<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roshan Angadia Service - Digital Ledger</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .header {
            text-align: center;
            background: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            margin-bottom: 20px;
        }

        .header h1 {
            color: #2c3e50;
            font-size: 28px;
            margin-bottom: 10px;
        }

        .header p {
            color: #7f8c8d;
            font-size: 16px;
            margin: 5px 0;
        }

        .route-selector {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .route-btn {
            padding: 15px 30px;
            border: 2px solid #3498db;
            border-radius: 25px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            background: white;
            color: #3498db;
        }

        .route-btn.active {
            background: #3498db;
            color: white;
        }

        .route-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(52, 152, 219, 0.3);
        }

        .ledger-container {
            background: white;
            border-radius: 15px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            overflow: hidden;
            margin-bottom: 20px;
        }

        .ledger-header {
            background: linear-gradient(135deg, #2c3e50, #34495e);
            color: white;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
        }

        .date-inputs {
            display: flex;
            gap: 15px;
            align-items: center;
            flex-wrap: wrap;
        }

        .date-inputs input, .date-inputs select {
            padding: 10px 15px;
            border: none;
            border-radius: 8px;
            font-size: 14px;
            background: #ecf0f1;
        }

        .add-entry-btn {
            background: #27ae60;
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 25px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .add-entry-btn:hover {
            background: #229954;
            transform: translateY(-2px);
        }

        .table-container {
            overflow-x: auto;
            max-height: 70vh;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 14px;
        }

        th, td {
            padding: 12px 8px;
            text-align: left;
            border-bottom: 1px solid #ecf0f1;
        }

        th {
            background: #f8f9fa;
            font-weight: bold;
            color: #2c3e50;
            position: sticky;
            top: 0;
            z-index: 10;
            white-space: nowrap;
        }

        /* Column widths as specified */
        .sender-col { width: 12%; }
        .parcels-col { width: 8%; }
        .insurance-col { width: 8%; }
        .receiver-col { width: 22%; } /* Widest column */
        .vp-col { width: 9%; }
        .weight-col { width: 9%; }
        .charged-col { width: 9%; }
        .payment-col { width: 10%; }
        .remarks-col { width: 13%; }

        input, select {
            width: 100%;
            padding: 6px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 13px;
        }

        .payment-select {
            min-width: 90px;
            background: white;
        }

        .delete-btn {
            background: #e74c3c;
            color: white;
            border: none;
            padding: 6px 10px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 12px;
        }

        .delete-btn:hover {
            background: #c0392b;
        }

        .total-row {
            background: #3498db !important;
            color: white;
            font-weight: bold;
            font-size: 16px;
        }

        .route-title {
            font-size: 24px;
            font-weight: bold;
            color: #2c3e50;
            padding: 20px;
            text-align: center;
            background: #f8f9fa;
        }

        .print-section {
            text-align: center;
            padding: 20px;
        }

        .print-btn {
            background: #f39c12;
            color: white;
            border: none;
            padding: 18px 40px;
            border-radius: 30px;
            font-size: 20px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .print-btn:hover {
            background: #e67e22;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(243, 156, 18, 0.4);
        }

        @media print {
            body { background: white; padding: 0; }
            .route-selector, .add-entry-btn, .print-btn, .delete-btn { display: none !important; }
            input, select { border: none !important; background: white !important; }
            .ledger-container { box-shadow: none; margin: 0; }
            .route-title { background: #f0f0f0; }
        }

        .pricing-info {
            background: #e8f5e8;
            padding: 15px;
            margin: 10px 20px;
            border-radius: 8px;
            border-left: 5px solid #27ae60;
        }

        .pricing-info h3 {
            color: #27ae60;
            margin-bottom: 8px;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>🛡️ Roshan Angadia Service</h1>
        <p><strong>Owned by:</strong> Haji Yunusbhai Sulemanbhai Vhora and Sons</p>
        <p>📍 Shop No. 45, Corporation Bank, Raja Complex, Station Road, Khambhat - 388620</p>
    </div>

    <div class="pricing-info">
        <h3>💰 Pricing Rules:</h3>
        <p><strong>👜 Bags:</strong> ₹5/kg | <strong>📦 Parcel:</strong> ₹30/kg | <strong>Minimum:</strong> ₹200</p>
        <p><em>Insurance & V.P. add 10% extra charge (optional)</em></p>
    </div>

    <div class="route-selector">
        <button class="route-btn active" onclick="switchRoute('jaipur-khambhat')">
            Jaipur → Khambhat
        </button>
        <button class="route-btn" onclick="switchRoute('khambhat-jaipur')">
            Khambhat → Jaipur
        </button>
    </div>

    <div class="ledger-container" id="ledgerContainer">
        <div class="ledger-header">
            <div class="date-inputs">
                <input type="date" id="entryDate" onchange="updateHeader()">
                <select id="dayOfWeek">
                    <option value="Monday">Monday</option>
                    <option value="Tuesday">Tuesday</option>
                    <option value="Wednesday">Wednesday</option>
                    <option value="Thursday">Thursday</option>
                    <option value="Friday">Friday</option>
                    <option value="Saturday">Saturday</option>
                    <option value="Sunday">Sunday</option>
                </select>
                <span>Page: <span id="pageNumber">1</span></span>
            </div>
            <button class="add-entry-btn" onclick="addNewEntry()">➕ Add New Entry</button>
        </div>

        <div class="route-title" id="routeTitle">Jaipur → Khambhat</div>
        
        <div class="table-container">
            <table id="ledgerTable">
                <thead>
                    <tr>
                        <th class="sender-col">Sender's Name</th>
                        <th class="parcels-col">No. of Bags/Parcels</th>
                        <th class="insurance-col">Insurance (₹)</th>
                        <th class="receiver-col">Receiver's Name</th>
                        <th class="vp-col">V.P. Amount (₹)</th>
                        <th class="weight-col">Weight (kg)</th>
                        <th class="charged-col">Charged (₹)</th>
                        <th class="payment-col">Payment Status</th>
                        <th class="remarks-col">Remarks</th>
                    </tr>
                </thead>
                <tbody id="tableBody"></tbody>
                <tfoot>
                    <tr class="total-row">
                        <td colspan="6"><strong>TOTAL</strong></td>
                        <td id="totalCharged">₹0</td>
                        <td id="totalPaid" colspan="2">₹0</td>
                    </tr>
                </tfoot>
            </table>
        </div>
    </div>

    <div class="print-section">
        <button class="print-btn" onclick="window.print()">
            📄 Print & Save as PDF
        </button>
    </div>

    <script>
        let currentRoute = 'jaipur-khambhat';
        let entries = [];
        let entryCounter = 0;

        // Initialize
        document.getElementById('entryDate').value = new Date().toISOString().split('T')[0];
        loadData();
        updateDayOfWeek();
        renderTable();

        function updateDayOfWeek() {
            const date = new Date(document.getElementById('entryDate').value);
            const days = ['Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturday'];
            document.getElementById('dayOfWeek').value = days[date.getDay()];
        }

        function updateHeader() {
            updateDayOfWeek();
        }

        function switchRoute(route) {
            // Save current route data first
            saveData();
            
            currentRoute = route;
            loadData();
            
            document.querySelectorAll('.route-btn').forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');
            
            document.getElementById('routeTitle').textContent = 
                route === 'jaipur-khambhat' ? 'Jaipur → Khambhat' : 'Khambhat → Jaipur';
            
            renderTable();
        }

        function calculateCharges(type, weight, insurance = 0, vp = 0) {
            const baseRate = type === 'bags' ? 5 : 30;
            let baseCharge = Math.max(weight * baseRate, 200);
            const extraCharge = Math.round((insurance + vp) * 0.1);
            return baseCharge + extraCharge;
        }

        function addNewEntry() {
            const newEntry = {
                id: ++entryCounter,
                date: document.getElementById('entryDate').value,
                day: document.getElementById('dayOfWeek').value,
                sender: '',
                type: 'bags',
                parcels: 1,
                insurance: 0,
                receiver: '',
                vp: 0,
                weight: 0,
                charged: 0,
                payment: 'unpaid',
                remarks: ''
            };
            
            entries.push(newEntry);
            saveData();
            renderTable();
        }

        function saveData() {
            const allData = JSON.parse(localStorage.getItem('roshanAngadiaLedger') || '{}');
            allData[currentRoute] = {
                entries: entries,
                counter: entryCounter
            };
            localStorage.setItem('roshanAngadiaLedger', JSON.stringify(allData));
        }

        function loadData() {
            const allData = JSON.parse(localStorage.getItem('roshanAngadiaLedger') || '{}');
            const routeData = allData[currentRoute];
            if (routeData) {
                entries = routeData.entries || [];
                entryCounter = routeData.counter || 0;
            } else {
                entries = [];
                entryCounter = 0;
            }
        }

        function deleteEntry(id) {
            entries = entries.filter(entry => entry.id !== id);
            saveData();
            renderTable();
        }

        function updateEntry(index) {
            const entry = entries[index];
            const type = document.querySelector(`#type-${entry.id}`).value;
            const parcels = parseInt(document.querySelector(`#parcels-${entry.id}`).value) || 1;
            const weight = parseFloat(document.querySelector(`#weight-${entry.id}`).value) || 0;
            const insurance = parseFloat(document.querySelector(`#insurance-${entry.id}`).value) || 0;
            const vp = parseFloat(document.querySelector(`#vp-${entry.id}`).value) || 0;
            
            entry.type = type;
            entry.parcels = parcels;
            entry.weight = weight;
            entry.insurance = insurance;
            entry.vp = vp;
            entry.charged = calculateCharges(type, weight, insurance, vp);
            
            // Update text fields
            entry.sender = document.querySelector(`#sender-${entry.id}`).value;
            entry.receiver = document.querySelector(`#receiver-${entry.id}`).value;
            entry.payment = document.querySelector(`#payment-${entry.id}`).value;
            entry.remarks = document.querySelector(`#remarks-${entry.id}`).value;
            
            saveData();
            renderTable();
        }

        function renderTable() {
            const tbody = document.getElementById('tableBody');
            tbody.innerHTML = '';
            
            let totalCharged = 0;
            let totalPaid = 0;
            
            entries.forEach((entry, index) => {
                totalCharged += entry.charged;
                if (['cash', 'account', 'gpay'].includes(entry.payment)) {
                    totalPaid += entry.charged;
                }
                
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td><input type="text" id="sender-${entry.id}" value="${entry.sender || ''}" onchange="updateEntry(${index})"></td>
                    <td>
                        <select id="type-${entry.id}" onchange="updateEntry(${index})" style="width:60px;margin-right:5px;">
                            <option value="bags" ${entry.type === 'bags' ? 'selected' : ''}>Bags</option>
                            <option value="parcel" ${entry.type === 'parcel' ? 'selected' : ''}>Parcel</option>
                        </select>
                        <input type="number" id="parcels-${entry.id}" value="${entry.parcels || 1}" min="1" onchange="updateEntry(${index})" style="width:50px;">
                    </td>
                    <td><input type="number" id="insurance-${entry.id}" value="${entry.insurance || 0}" min="0" onchange="updateEntry(${index})"></td>
                    <td><input type="text" id="receiver-${entry.id}" value="${entry.receiver || ''}" onchange="updateEntry(${index})"></td>
                    <td><input type="number" id="vp-${entry.id}" value="${entry.vp || 0}" min="0" onchange="updateEntry(${index})"></td>
                    <td><input type="number" id="weight-${entry.id}" value="${entry.weight || 0}" step="0.01" min="0" onchange="updateEntry(${index})"></td>
                    <td><strong>₹${entry.charged}</strong></td>
                    <td>
                        <select id="payment-${entry.id}" class="payment-select" onchange="updateEntry(${index})">
                            <option value="unpaid" ${entry.payment === 'unpaid' ? 'selected' : ''}>Unpaid</option>
                            <option value="cash" ${entry.payment === 'cash' ? 'selected' : ''}>Cash</option>
                            <option value="account" ${entry.payment === 'account' ? 'selected' : ''}>Account</option>
                            <option value="gpay" ${entry.payment === 'gpay' ? 'selected' : ''}>GPay</option>
                        </select>
                    </td>
                    <td><input type="text" id="remarks-${entry.id}" value="${entry.remarks || ''}" onchange="updateEntry(${index})"></td>
                `;
                tbody.appendChild(row);
            });
            
            document.getElementById('totalCharged').textContent = `₹${totalCharged}`;
            document.getElementById('totalPaid').textContent = `₹${totalPaid}`;
            document.getElementById('pageNumber').textContent = Math.ceil((entries.length + 1) / 20);
        }
    </script>
</body>
</html>
