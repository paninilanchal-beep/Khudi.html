<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Monthly Autopay Setup</title>
    <style>
        :root {
            --primary-color: #e23744; /* A warm, app-style primary color */
            --bg-color: #f8f9fa;
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

        .autopay-container {
            background-color: var(--card-bg);
            width: 100%;
            max-width: 400px;
            border-radius: 16px;
            box-shadow: 0 8px 24px rgba(0,0,0,0.08);
            overflow: hidden;
        }

        .header {
            background-color: var(--primary-color);
            color: white;
            padding: 24px 20px;
            text-align: center;
        }

        .header h2 {
            font-size: 22px;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .header p {
            font-size: 14px;
            opacity: 0.9;
        }

        .content {
            padding: 24px 20px;
        }

        .detail-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 16px 0;
            border-bottom: 1px solid var(--border-color);
        }

        .detail-row:last-of-type {
            border-bottom: none;
            margin-bottom: 16px;
        }

        .label {
            color: var(--text-muted);
            font-size: 14px;
        }

        .value {
            color: var(--text-main);
            font-size: 15px;
            font-weight: 600;
            text-align: right;
        }

        .highlight {
            color: var(--primary-color);
            font-weight: 700;
            font-size: 16px;
        }

        .security-badge {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            color: #28a745;
            font-size: 13px;
            margin-bottom: 24px;
            background: #eafbee;
            padding: 10px;
            border-radius: 8px;
        }

        .btn-submit {
            width: 100%;
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 16px;
            font-size: 16px;
            font-weight: 600;
            border-radius: 12px;
            cursor: pointer;
            transition: background-color 0.2s;
        }

        .btn-submit:hover {
            background-color: #c9303d;
        }

        .btn-submit:active {
            transform: scale(0.98);
        }

        .footer-note {
            text-align: center;
            font-size: 12px;
            color: var(--text-muted);
            margin-top: 16px;
        }
    </style>
</head>
<body>

    <div class="autopay-container">
        <div class="header">
            <h2>Set Up Autopay</h2>
            <p>Hassle-free monthly payments</p>
        </div>

        <div class="content">
            <div class="security-badge">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path>
                </svg>
                Secure UPI Mandate
            </div>

            <div class="detail-row">
                <span class="label">Billed To Number</span>
                <span class="value">9348854171</span>
            </div>
            
            <div class="detail-row">
                <span class="label">Billing Cycle</span>
                <span class="value">Monthly</span>
            </div>

            <div class="detail-row">
                <span class="label">Deduction Date</span>
                <span class="value highlight">1st of every month</span>
            </div>

            <button class="btn-submit" onclick="initiateAutopay()">Authorize Autopay</button>

            <p class="footer-note">By authorizing, you allow automatic deductions on the 1st of every month. You can cancel anytime.</p>
        </div>
    </div>

    <script>
        function initiateAutopay() {
            // This is where you will integrate your payment gateway's subscription API
            // Example: Razorpay Subscription link or UPI AutoPay intent link
            const phoneNumber = "9348854171";
            
            alert(`Initiating secure UPI Autopay setup for number: ${phoneNumber}.\nBilling Date: 1st of the month.\n\n(Note: Connect your payment gateway API here to complete the mandate.)`);
            
            // Redirect example:
            // window.location.href = "YOUR_PAYMENT_GATEWAY_LINK";
        }
    </script>
</body>
</html>
