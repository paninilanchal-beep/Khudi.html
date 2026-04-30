<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Setup Monthly Subscription</title>
    <style>
        :root {
            --phonepe-purple: #5f259f;
            --bg-color: #f4f6f8;
            --card-bg: #ffffff;
            --text-main: #1c1c1c;
            --text-muted: #666666;
            --border-color: #e8e8e8;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        .subscription-card {
            background-color: var(--card-bg);
            width: 100%;
            max-width: 380px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            overflow: hidden;
            text-align: center;
        }

        .header {
            background-color: var(--phonepe-purple);
            color: white;
            padding: 30px 20px;
        }

        .header h1 {
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .header p {
            font-size: 15px;
            opacity: 0.9;
        }

        .content {
            padding: 30px 20px;
        }

        .business-name {
            font-size: 18px;
            font-weight: 600;
            color: var(--text-main);
            margin-bottom: 20px;
        }

        .details {
            background: #f9f9f9;
            border-radius: 12px;
            padding: 15px;
            margin-bottom: 25px;
            text-align: left;
        }

        .detail-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 14px;
        }

        .detail-row:last-child {
            margin-bottom: 0;
        }

        .detail-row .label {
            color: var(--text-muted);
        }

        .detail-row .value {
            font-weight: 600;
            color: var(--text-main);
        }

        .btn-phonepe {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            width: 100%;
            background-color: var(--phonepe-purple);
            color: white;
            border: none;
            padding: 16px;
            font-size: 16px;
            font-weight: 600;
            border-radius: 12px;
            cursor: pointer;
            transition: opacity 0.2s;
            text-decoration: none;
        }

        .btn-phonepe:active {
            opacity: 0.8;
            transform: scale(0.98);
        }

        .footer-note {
            font-size: 12px;
            color: var(--text-muted);
            margin-top: 20px;
            line-height: 1.5;
        }
    </style>
</head>
<body>

    <div class="subscription-card">
        <div class="header">
            <h1>₹2,000</h1>
            <p>per month</p>
        </div>

        <div class="content">
            <div class="business-name">Pami and Khudi Tiffin Services</div>
            
            <div class="details">
                <div class="detail-row">
                    <span class="label">Billed To</span>
                    <span class="value">9348854171@ybl</span>
                </div>
                <div class="detail-row">
                    <span class="label">Billing Cycle</span>
                    <span class="value">Monthly</span>
                </div>
                <div class="detail-row">
                    <span class="label">Auto-Deduction</span>
                    <span class="value" style="color: var(--phonepe-purple);">1st of every month</span>
                </div>
            </div>

            <button class="btn-phonepe" onclick="openPhonePe()">
                Set up Autopay on PhonePe
            </button>

            <p class="footer-note">
                Clicking the button will open your PhonePe app to authorize the monthly mandate. 
            </p>
        </div>
    </div>

    <script>
        function openPhonePe() {
            // Payee details
            const upiId = "9348854171@ybl";
            const payeeName = encodeURIComponent("Pami and Khudi Tiffin Services");
            const amount = "2000.00";
            const transactionNote = encodeURIComponent("Monthly Autopay Setup - 1st of the month");

            // Standard UPI Deep Link 
            // Note: True recurring mandates (upi://mandate) usually require a signed payload from a payment gateway like PhonePe Business. 
            // This link forces the phonepe app to open and pre-fills the payment data.
            const upiIntentURL = `phonepe://pay?pa=${upiId}&pn=${payeeName}&am=${amount}&tn=${transactionNote}&cu=INR`;

            // Fallback for non-PhonePe users or standard UPI apps
            const standardUpiURL = `upi://pay?pa=${upiId}&pn=${payeeName}&am=${amount}&tn=${transactionNote}&cu=INR`;

            // Attempt to open PhonePe directly
            window.location.href = upiIntentURL;

            // Optional: If you want it to fall back to any UPI app if PhonePe isn't installed
            setTimeout(() => {
                window.location.href = standardUpiURL;
            }, 1500);
        }
    </script>
</body>
</html>
