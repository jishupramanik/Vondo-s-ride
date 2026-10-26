
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vondo's Ride - Login & Booking</title>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background: #f3f6fb;
    color: #172033;
}

button, input, select {
    font: inherit;
}

button {
    cursor: pointer;
}

.hidden {
    display: none !important;
}

header {
    background: #111827;
    color: white;
    padding: 20px 7%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    flex-wrap: wrap;
}

.logo {
    font-size: 25px;
    font-weight: bold;
}

.logo span {
    color: #fbbf24;
}

header p {
    color: #d1d5db;
    font-size: 14px;
}

.hero {
    background: linear-gradient(120deg, #172554, #2563eb);
    color: white;
    padding: 45px 7%;
    text-align: center;
}

.hero h1 {
    font-size: clamp(30px, 5vw, 45px);
    margin-bottom: 12px;
}

.hero p {
    color: #dbeafe;
    line-height: 1.7;
}

.container {
    max-width: 1000px;
    margin: 30px auto;
    padding: 0 18px;
}

.panel {
    background: white;
    border-radius: 16px;
    padding: 25px;
    margin-bottom: 25px;
    box-shadow: 0 5px 22px #1720330c;
}

h2 {
    margin-bottom: 20px;
    font-size: 23px;
}

.login-screen {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 25px 16px;
    background:
        radial-gradient(circle at top left, #dbeafe, transparent 45%),
        linear-gradient(135deg, #f8fafc, #e0e7ff);
}

.login-card {
    width: 100%;
    max-width: 430px;
    padding: 32px;
    border-radius: 20px;
    background: white;
    box-shadow: 0 20px 60px #17255418;
}

.login-brand {
    text-align: center;
    margin-bottom: 28px;
}

.login-icon {
    width: 68px;
    height: 68px;
    border-radius: 20px;
    background: #dbeafe;
    display: grid;
    place-items: center;
    margin: 0 auto 16px;
    font-size: 35px;
}

.login-brand h1 {
    font-size: 29px;
    margin-bottom: 8px;
}

.login-brand h1 span {
    color: #2563eb;
}

.login-brand p {
    color: #64748b;
    line-height: 1.6;
}

.field {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-bottom: 17px;
}

label {
    font-size: 14px;
    font-weight: 600;
}

input, select {
    width: 100%;
    padding: 13px;
    border: 1px solid #d1d5db;
    border-radius: 9px;
    background: white;
    color: #172033;
}

input:focus, select:focus {
    outline: 2px solid #93c5fd;
    border-color: #2563eb;
}

.password-wrap {
    display: flex;
    gap: 8px;
}

.password-wrap input {
    min-width: 0;
}

.small-btn {
    border: 1px solid #d1d5db;
    background: white;
    border-radius: 9px;
    padding: 0 12px;
    color: #334155;
}

.btn {
    width: 100%;
    border: none;
    border-radius: 9px;
    padding: 14px;
    background: #2563eb;
    color: white;
    font-weight: bold;
    font-size: 16px;
    margin-top: 5px;
}

.btn:hover {
    background: #1d4ed8;
}

.link-btn {
    border: none;
    background: transparent;
    color: #2563eb;
    font-weight: bold;
    padding: 10px 4px;
}

.login-switch {
    text-align: center;
    margin-top: 18px;
    color: #64748b;
    font-size: 14px;
}

.login-notice {
    margin-top: 18px;
    font-size: 12px;
    color: #64748b;
    line-height: 1.6;
    text-align: center;
}

.error {
    color: #b91c1c;
    font-size: 13px;
    line-height: 1.5;
    margin-bottom: 12px;
}

.categories {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
    margin-bottom: 24px;
}

.category {
    border: 2px solid #e5e7eb;
    background: white;
    padding: 18px 8px;
    border-radius: 12px;
    font-weight: bold;
}

.category.active {
    border-color: #2563eb;
    background: #eff6ff;
    color: #1d4ed8;
}

.vehicle-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
    gap: 14px;
}

.vehicle {
    border: 2px solid #e5e7eb;
    border-radius: 12px;
    padding: 18px;
    cursor: pointer;
}

.vehicle:hover {
    border-color: #93c5fd;
}

.vehicle.selected {
    border-color: #2563eb;
    background: #eff6ff;
}

.vehicle .emoji {
    font-size: 32px;
    margin-bottom: 12px;
}

.vehicle h3 {
    font-size: 16px;
    margin-bottom: 9px;
}

.price {
    font-size: 18px;
    color: #1d4ed8;
    font-weight: bold;
}

.muted {
    color: #6b7280;
    font-size: 13px;
    margin-top: 5px;
}

form.booking-form {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 18px;
}

.booking-form .field {
    margin-bottom: 0;
}

.field.full {
    grid-column: 1 / -1;
}

.summary {
    background: #eff6ff;
    padding: 20px;
    border-radius: 12px;
    margin-top: 8px;
}

.summary h2 {
    margin-bottom: 14px;
}

.summary-row {
    display: flex;
    justify-content: space-between;
    gap: 12px;
    margin: 10px 0;
}

.total {
    border-top: 1px solid #bfdbfe;
    padding-top: 14px;
    margin-top: 14px;
    font-size: 21px;
    font-weight: bold;
}

.notice {
    font-size: 13px;
    line-height: 1.6;
    color: #6b7280;
    margin-top: 15px;
}

#result {
    display: none;
    border: 1px solid #86efac;
    background: #f0fdf4;
    border-radius: 12px;
    padding: 20px;
    margin-top: 20px;
    line-height: 1.8;
    overflow-wrap: anywhere;
}

#result button {
    margin-top: 15px;
}

footer {
    background: #111827;
    color: #d1d5db;
    text-align: center;
    padding: 25px;
    font-size: 14px;
}

@media (max-width: 600px) {
    header {
        padding: 20px;
    }

    .login-card {
        padding: 24px;
    }

    .hero {
        padding: 35px 20px;
    }

    .panel {
        padding: 18px;
    }

    form.booking-form {
        grid-template-columns: 1fr;
    }

    .field.full {
        grid-column: auto;
    }
}
</style>
</head>

<body>

<!-- LOGIN / REGISTRATION SCREEN -->
<section id="loginScreen" class="login-screen">
    <div class="login-card">
        <div class="login-brand">
            <div class="login-icon">🚘</div>
            <h1>Vondo's <span>Ride</span></h1>
            <p id="loginSubtitle">Login to book your next ride</p>
        </div>

        <form id="loginForm">
            <div class="field">
                <label for="loginEmail">Email Address</label>
                <input id="loginEmail" type="email"
                    placeholder="you@example.com" autocomplete="username"
                    required>
            </div>

            <div class="field">
                <label for="loginPassword">Password</label>
                <div class="password-wrap">
                    <input id="loginPassword" type="password"
                        placeholder="Enter password"
                        autocomplete="current-password"
                        minlength="6" required>
                    <button type="button" class="small-btn"
                        id="togglePassword">Show</button>
                </div>
            </div>

            <div id="loginError" class="error" role="alert"></div>

            <button class="btn" type="submit" id="loginSubmit">
                Login
            </button>

            <div class="login-switch">
                <span id="switchText">Don't have an account?</span>
                <button type="button" class="link-btn" id="switchMode">
                    Create Account
                </button>
            </div>

            <p class="login-notice">
                Demo login only. Accounts are not securely stored.
                Do not use a real password on this demo website.
            </p>
        </form>
    </div>
</section>

<!-- MAIN RENTAL WEBSITE -->
<div id="appScreen" class="hidden">
    <header>
        <div class="logo">Vondo's <span>Ride</span></div>
        <div style="display:flex;align-items:center;gap:14px">
            <p id="welcomeUser">Welcome!</p>
            <button id="logoutBtn" class="small-btn"
                style="padding:10px 14px">Logout</button>
        </div>
    </header>

    <section class="hero">
        <h1>Find Your Perfect Ride</h1>
        <p>Choose your vehicle, select your pickup time, and book your ride.</p>
    </section>

    <main class="container">
        <section class="panel">
            <h2>1. Choose a Vehicle</h2>

            <div class="categories">
                <button type="button" class="category active"
                    data-category="Bike">🏍️ Bikes</button>
                <button type="button" class="category"
                    data-category="Scooty">🛵 Scooties</button>
                <button type="button" class="category"
                    data-category="Car">🚗 Cars</button>
            </div>

            <div id="vehicleGrid" class="vehicle-grid"></div>
        </section>

        <section class="panel">
            <h2>2. Your Booking Details</h2>

            <form id="bookingForm" class="booking-form">
                <div class="field">
                    <label for="customerName">Full Name</label>
                    <input id="customerName" required maxlength="100"
                        placeholder="Enter your name">
                </div>

                <div class="field">
                    <label for="mobile">Mobile Number</label>
                    <input id="mobile" type="tel" inputmode="numeric"
                        pattern="[0-9]{10}" maxlength="10" required
                        placeholder="10-digit mobile number">
                </div>

                <div class="field">
                    <label for="pickupDate">Pickup Date</label>
                    <input id="pickupDate" type="date" required>
                </div>

                <div class="field">
                    <label for="pickupTime">Pickup Time</label>
                    <input id="pickupTime" type="time" required>
                </div>

                <div class="field full">
                    <label for="days">Rental Duration</label>
                    <select id="days" required>
                        <option value="1">1 day</option>
                        <option value="2">2 days</option>
                        <option value="3">3 days</option>
                        <option value="4">4 days</option>
                        <option value="5">5 days</option>
                        <option value="7">7 days</option>
                        <option value="10">10 days</option>
                        <option value="15">15 days</option>
                        <option value="30">30 days</option>
                    </select>
                </div>

                <div class="field full">
                    <div class="summary">
                        <h2>Booking Summary</h2>

                        <div class="summary-row">
                            <span>Selected vehicle</span>
                            <strong id="summaryVehicle"></strong>
                        </div>

                        <div class="summary-row">
                            <span>Price per day</span>
                            <strong id="dailyPrice"></strong>
                        </div>

                        <div class="summary-row">
                            <span>Rental duration</span>
                            <strong id="summaryDays"></strong>
                        </div>

                        <div class="summary-row total">
                            <span>Estimated total</span>
                            <span id="totalPrice"></span>
                        </div>
                    </div>
                </div>

                <div class="field full">
                    <button class="btn" type="submit">
                        Confirm Booking
                    </button>
                    <p class="notice">
                        This demo creates a booking request on this page.
                        It does not guarantee a real vehicle reservation.
                    </p>
                </div>
            </form>

            <div id="result" role="status" aria-live="polite"></div>
        </section>
    </main>

    <footer>
        <p>© 2026 Vondo's Ride. All rights reserved.</p>
        <p style="margin-top:8px">Ride safe. Travel smart.</p>
    </footer>
</div>

<script>
const vehicles = {
    Bike: [
        { name: "Hero Mavrick 440", price: 250 },
        { name: "Yamaha FZ 25", price: 260 },
        { name: "Bajaj Pulsar 150", price: 270 },
        { name: "TVS Apache RTR 310", price: 280 },
        { name: "KTM Duke 390", price: 300 },
        { name: "Honda CB Hornet 2.0", price: 290 },
        { name: "Royal Enfield Classic 350", price: 350 }
    ],
    Scooty: [
        { name: "Honda Activa 6G", price: 200 },
        { name: "Bajaj Chetak", price: 200 },
        { name: "TVS Jupiter", price: 210 },
        { name: "Suzuki Access 125", price: 220 },
        { name: "Yamaha Fascino 125", price: 230 },
        { name: "Hero Maestro Edge 125", price: 240 },
        { name: "Vespa SXL 150", price: 250 }
    ],
    Car: [
        { name: "Maruti Suzuki Swift", price: 500 },
        { name: "Hyundai i20", price: 550 },
        { name: "Tata Altroz", price: 600 },
        { name: "Kia Sonet", price: 650 },
        { name: "Mahindra XUV300", price: 700 },
        { name: "Honda City", price: 750 },
        { name: "Toyota Yaris", price: 800 }
    ]
};

let currentCategory = "Bike";
let selectedVehicle = vehicles.Bike[0];
let registrationMode = false;

// Demo-only account store. It resets when the page is refreshed.
const demoAccounts = new Map();

const loginScreen = document.getElementById("loginScreen");
const appScreen = document.getElementById("appScreen");
const loginForm = document.getElementById("loginForm");
const loginError = document.getElementById("loginError");
const loginEmail = document.getElementById("loginEmail");
const loginPassword = document.getElementById("loginPassword");
const grid = document.getElementById("vehicleGrid");
const daysInput = document.getElementById("days");
const dateInput = document.getElementById("pickupDate");
const bookingForm = document.getElementById("bookingForm");
const result = document.getElementById("result");

function showLoginError(message) {
    loginError.textContent = message;
}

function showApp(email) {
    loginScreen.classList.add("hidden");
    appScreen.classList.remove("hidden");
    document.getElementById("welcomeUser").textContent =
        "Welcome, " + email;
    loginPassword.value = "";
    showLoginError("");
}

document.getElementById("switchMode").addEventListener("click", () => {
    registrationMode = !registrationMode;

    document.getElementById("loginSubtitle").textContent =
        registrationMode ? "Create your demo account" :
                           "Login to book your next ride";

    document.getElementById("loginSubmit").textContent =
        registrationMode ? "Create Account" : "Login";

    document.getElementById("switchText").textContent =
        registrationMode ? "Already have an account?" :
                           "Don't have an account?";

    document.getElementById("switchMode").textContent =
        registrationMode ? "Login" : "Create Account";

    loginPassword.autocomplete =
        registrationMode ? "new-password" : "current-password";

    showLoginError("");
});

document.getElementById("togglePassword").addEventListener("click", () => {
    const hidden = loginPassword.type === "password";
    loginPassword.type = hidden ? "text" : "password";
    document.getElementById("togglePassword").textContent =
        hidden ? "Hide" : "Show";
});

loginForm.addEventListener("submit", event => {
    event.preventDefault();

    const email = loginEmail.value.trim().toLowerCase();
    const password = loginPassword.value;

    if (password.length < 6) {
        showLoginError("Password must contain at least 6 characters.");
        return;
    }

    if (registrationMode) {
        if (demoAccounts.has(email)) {
            showLoginError("An account with this email already exists.");
            return;
        }

        demoAccounts.set(email, password);
        showApp(email);
        return;
    }

    if (!demoAccounts.has(email)) {
        showLoginError("Demo account not found. Please create an account first.");
        return;
    }

    if (demoAccounts.get(email) !== password) {
        showLoginError("Incorrect password. Please try again.");
        return;
    }

    showApp(email);
});

document.getElementById("logoutBtn").addEventListener("click", () => {
    appScreen.classList.add("hidden");
    loginScreen.classList.remove("hidden");
    loginForm.reset();
    registrationMode = false;

    document.getElementById("loginSubtitle").textContent =
        "Login to book your next ride";
    document.getElementById("loginSubmit").textContent = "Login";
    document.getElementById("switchText").textContent =
        "Don't have an account?";
    document.getElementById("switchMode").textContent = "Create Account";
    loginPassword.type = "password";
    document.getElementById("togglePassword").textContent = "Show";
    showLoginError("");
});

function renderVehicles() {
    grid.replaceChildren();

    vehicles[currentCategory].forEach(vehicle => {
        const card = document.createElement("div");
        card.className = "vehicle" +
            (selectedVehicle.name === vehicle.name ? " selected" : "");

        const emoji = currentCategory === "Bike" ? "🏍️" :
                      currentCategory === "Scooty" ? "🛵" : "🚗";

        const icon = document.createElement("div");
        icon.className = "emoji";
        icon.textContent = emoji;

        const heading = document.createElement("h3");
        heading.textContent = vehicle.name;

        const price = document.createElement("div");
        price.className = "price";
        price.textContent = `₹${vehicle.price}/day`;

        const note = document.createElement("div");
        note.className = "muted";
        note.textContent = "Rental price";

        card.append(icon, heading, price, note);

        card.addEventListener("click", () => {
            selectedVehicle = vehicle;
            result.style.display = "none";
            renderVehicles();
            updateSummary();
        });

        grid.appendChild(card);
    });
}

document.querySelectorAll(".category").forEach(button => {
    button.addEventListener("click", () => {
        currentCategory = button.dataset.category;
        selectedVehicle = vehicles[currentCategory][0];

        document.querySelectorAll(".category").forEach(item => {
            item.classList.toggle("active", item === button);
        });

        result.style.display = "none";
        renderVehicles();
        updateSummary();
    });
});

function updateSummary() {
    const days = Number(daysInput.value);
    document.getElementById("summaryVehicle").textContent =
        selectedVehicle.name;
    document.getElementById("dailyPrice").textContent =
        `₹${selectedVehicle.price}`;
    document.getElementById("summaryDays").textContent =
        `${days} ${days === 1 ? "day" : "days"}`;
    document.getElementById("totalPrice").textContent =
        `₹${(selectedVehicle.price * days).toLocaleString("en-IN")}`;
}

daysInput.addEventListener("change", updateSummary);

const now = new Date();
const today = [
    now.getFullYear(),
    String(now.getMonth() + 1).padStart(2, "0"),
    String(now.getDate()).padStart(2, "0")
].join("-");

dateInput.min = today;
dateInput.value = today;

bookingForm.addEventListener("submit", event => {
    event.preventDefault();

    if (!bookingForm.reportValidity()) return;

    const pickupDate = dateInput.value;
    const pickupTime = document.getElementById("pickupTime")
        ? document.getElementById("pickupTime").value
        : "";

    // The booking form uses pickup date and time fields.
    const timeField = bookingForm.querySelector('input[type="time"]');
    const time = timeField ? timeField.value : "";

    if (!time) {
        alert("Please select a pickup time.");
        return;
    }

    const pickup = new Date(`${pickupDate}T${time}`);

    if (Number.isNaN(pickup.getTime()) || pickup < new Date()) {
        alert("Please select a future pickup date and time.");
        return;
    }

    const bookingId = "VR" + Date.now().toString().slice(-10);
    const days = Number(daysInput.value);
    const total = selectedVehicle.price * days;
    const name = document.getElementById("customerName").value.trim();
    const mobile = document.getElementById("mobile").value;

    result.replaceChildren();

    const heading = document.createElement("h3");
    heading.textContent = "Booking Request Created!";

    const details = document.createElement("p");
    details.style.marginTop = "12px";
    details.textContent =
        `Booking ID: ${bookingId} | Customer: ${name} | Mobile: ${mobile} | Vehicle: ${selectedVehicle.name} | Pickup: ${pickupDate} at ${time} | Duration: ${days} day(s) | Total: ₹${total.toLocaleString("en-IN")}`;

    const notice = document.createElement("p");
    notice.textContent =
        "This is a demo request. It has not been sent to the rental owner.";

    const emailButton = document.createElement("button");
    emailButton.type = "button";
    emailButton.className = "btn";
    emailButton.textContent = "Prepare Email to Rental Owner";

    emailButton.addEventListener("click", () => {
        const subject = `Vondo's Ride Booking ${bookingId}`;
        const body = [
            "New Vondo's Ride booking request",
            `Booking ID: ${bookingId}`,
            `Customer: ${name}`,
            `Mobile: ${mobile}`,
            `Category: ${currentCategory}`,
            `Vehicle: ${selectedVehicle.name}`,
            `Price per day: Rs. ${selectedVehicle.price}`,
            `Duration: ${days} day(s)`,
            `Pickup date: ${pickupDate}`,
            `Pickup time: ${time}`,
            `Estimated total: Rs. ${total}`
        ].join("\n");

        window.location.href =
            "mailto:jishupramanik300@gmail.com" +
            "?subject=" + encodeURIComponent(subject) +
            "&body=" + encodeURIComponent(body);
    });

    result.append(heading, details, notice, emailButton);
    result.style.display = "block";
    result.scrollIntoView({ behavior: "smooth", block: "center" });
});

renderVehicles();
updateSummary();
</script>

</body>
</html>
# Vondo-s-ride
