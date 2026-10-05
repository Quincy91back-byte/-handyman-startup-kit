# -handyman-startup-kit
    $0 Handyman Startup Kit mobile app
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>$0 Handyman Startup Kit</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #f3f4f6;
    color: #111827;
}

header {
    background: #111827;
    color: white;
    padding: 25px 18px;
}

header h1 {
    margin: 0 0 8px;
    font-size: 28px;
}

header p {
    margin: 0;
    color: #d1d5db;
}

nav {
    display: flex;
    overflow-x: auto;
    background: white;
    border-bottom: 1px solid #ddd;
}

nav button {
    border: none;
    background: white;
    padding: 15px;
    font-weight: bold;
    white-space: nowrap;
}

main {
    max-width: 700px;
    margin: auto;
    padding: 18px;
}

.section {
    background: white;
    padding: 18px;
    margin-bottom: 18px;
    border-radius: 15px;
    box-shadow: 0 2px 8px #00000015;
}

input, textarea {
    width: 100%;
    padding: 12px;
    margin: 7px 0 15px;
    border: 1px solid #ccc;
    border-radius: 9px;
    font-size: 16px;
    box-sizing: border-box;
}

button.action {
    width: 100%;
    padding: 14px;
    background: #111827;
    color: white;
    border: none;
    border-radius: 10px;
    font-size: 16px;
    font-weight: bold;
}

.result {
    margin-top: 15px;
    padding: 15px;
    background: #f3f4f6;
    border-radius: 10px;
    font-size: 20px;
    font-weight: bold;
}

.ad {
    white-space: pre-wrap;
    background: #f3f4f6;
    padding: 15px;
    border-radius: 10px;
    line-height: 1.5;
}
</style>
</head>

<body>

<header>
<h1>🔨 $0 Handyman Startup Kit</h1>
<p>Tools to help you start and grow your handyman side hustle.</p>
</header>

<nav>
<button onclick="show('price')">💰 Pricing</button>
<button onclick="show('estimate')">🧾 Estimate</button>
<button onclick="show('ads')">📢 Ads</button>
<button onclick="show('guide')">📚 Guide</button>
</nav>

<main>

<div id="price" class="section">
<h2>💰 Job Price Calculator</h2>

<label>Labor Hours</label>
<input id="hours" type="number" value="2">

<label>Hourly Rate</label>
<input id="rate" type="number" value="50">

<label>Materials</label>
<input id="materials" type="number" value="25">

<label>Travel / Other Costs</label>
<input id="travel" type="number" value="10">

<button class="action" onclick="calculatePrice()">
Calculate Price
</button>

<div id="priceResult" class="result">
$135.00
</div>
</div>


<div id="estimate" class="section" style="display:none">

<h2>🧾 Customer Estimate</h2>

<label>Customer Name</label>
<input id="customer" placeholder="Customer name">

<label>Job Description</label>
<textarea id="job" placeholder="Describe the job"></textarea>

<label>Labor</label>
<input id="laborCost" type="number" value="100">

<label>Materials</label>
<input id="materialCost" type="number" value="50">

<label>Travel / Other</label>
<input id="otherCost" type="number" value="25">

<button class="action" onclick="createEstimate()">
Create Estimate
</button>

<div id="estimateResult" class="result"></div>

</div>


<div id="ads" class="section" style="display:none">

<h2>📢 Ready-to-Post Advertisement</h2>

<div class="ad" id="advertisement">
🔨 NEED A HANDYMAN?

I provide reliable handyman, plumbing, repair, installation and maintenance services.

✅ Plumbing repairs
✅ Toilet installation
✅ Faucet installation
✅ General repairs
✅ Home improvement
✅ Honest and affordable service

📍 Serving Tupelo and surrounding areas

📩 Message me today for a quote!

Let's get your project done right.
</div>

<br>

<button class="action" onclick="copyAd()">
Copy Advertisement
</button>

</div>


<div id="guide" class="section" style="display:none">

<h2>📚 Start Your Handyman Business</h2>

<p>1️⃣ Choose services you can safely and legally perform.</p>

<p>2️⃣ Create a simple price list.</p>

<p>3️⃣ Take before-and-after pictures.</p>

<p>4️⃣ Advertise on Facebook Marketplace and local groups where permitted.</p>

<p>5️⃣ Keep track of customers, expenses and income.</p>

<p>6️⃣ Check your local licensing, permit, insurance and tax requirements.</p>

<h3>💵 Simple Pricing Formula</h3>

<p><strong>
Labor + Materials + Travel + Profit = Customer Price
</strong></p>

</div>

</main>

<script>

function show(section) {

document.getElementById("price").style.display = "none";
document.getElementById("estimate").style.display = "none";
document.getElementById("ads").style.display = "none";
document.getElementById("guide").style.display = "none";

document.getElementById(section).style.display = "block";

}

function calculatePrice() {

let hours = Number(document.getElementById("hours").value);
let rate = Number(document.getElementById("rate").value);
let materials = Number(document.getElementById("materials").value);
let travel = Number(document.getElementById("travel").value);

let total = (hours * rate) + materials + travel;

document.getElementById("priceResult").innerText =
"$" + total.toFixed(2);

}

function createEstimate() {

let customer =
document.getElementById("customer").value || "Customer";

let job =
document.getElementById("job").value || "Handyman Service";

let labor =
Number(document.getElementById("laborCost").value);

let materials =
Number(document.getElementById("materialCost").value);

let other =
Number(document.getElementById("otherCost").value);

let total = labor + materials + other;

document.getElementById("estimateResult").innerText =
"ESTIMATE\n\n" +
"Customer: " + customer +
"\nJob: " + job +
"\n\nLabor: $" + labor.toFixed(2) +
"\nMaterials: $" + materials.toFixed(2) +
"\nTravel/Other: $" + other.toFixed(2) +
"\n\nTOTAL: $" + total.toFixed(2);

}

function copyAd() {

let text =
document.getElementById("advertisement").innerText;

navigator.clipboard.writeText(text);

alert("Advertisement copied!");

}

</script>

</body>
</html>
