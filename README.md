Here is my code:







<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
    <title>FoodNearU</title>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Dancing+Script:wght@400;600;700&family=Great+Vibes&family=Comfortaa:wght@400;600;700&family=Montserrat:wght@400;600;700&family=Lobster&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #2e7d32;
            color: white;
            text-align: center;
            padding: 15px;
            position: relative;
        }
        .login-link {
            position: absolute;
            top: 15px;
            right: 20px;
            color: #20b2aa;
            text-decoration: none;
            font-size: 16px;
            font-weight: bold;
        }
        .login-link:hover {
            text-decoration: underline;
        }
        .award-points-link {
            color: #20b2aa;
            text-decoration: none;
            font-size: 16px;
            position: absolute;
            top: 20px;
            right: 20px;
        }
        .award-points-link:hover {
            text-decoration: underline;
        }
        .status-link {
            color: #20b2aa;
            text-decoration: none;
            font-size: 16px;
            position: absolute;
            top: 20px;
            right: 200px;
        }
        .status-link:hover {
            text-decoration: underline;
        }
        .donors-tab-header {
            position: relative;
            padding: 20px;
        }
        nav {
            display: flex;
            justify-content: center;
            background-color: #1b5e20;
        }
        nav a {
            padding: 15px 20px;
            text-decoration: none;
            color: white;
            font-size: 18px;
        }
        nav a:hover {
            background-color: #20b2aa;
        }
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
        }
        .form-group {
            margin-bottom: 15px;
        }
        label {
            font-weight: bold;
        }
        input, select, textarea {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        button {
            background-color: #20b2aa;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #1e9e96;
        }
        #search-food-btn {
            background-color: #90EE90;
            color: black;
        }
        #search-food-btn:hover {
            background-color: #7FDD7F;
        }
        .form-container {
            background-color: #fff;
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
        }

        /* Chatbot Styles */
        .chatbot {
            max-width: 100%;
            margin: 0;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 8px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            backdrop-filter: blur(5px);
        }
        .chat-box {
            height: 400px;
            overflow-y: auto;
            border: 1px solid #ccc;
            padding: 10px;
            margin-bottom: 10px;
            background: #fafafa;
            width: 100%;
            box-sizing: border-box;
        }
        
        #chat-input {
            width: calc(100% - 80px);
            padding: 10px;
            margin-right: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        
        #chat-send {
            width: 70px;
            padding: 10px;
            background-color: #2e7d32;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        
        #chat-send:hover {
            background-color: #1b5e20;
        }
        .chat-msg {
            margin-bottom: 10px;
        }
        .chat-msg.user {
            text-align: right;
        }
        .chat-msg.bot {
            text-align: left;
        }
        h2 {
            color: #2c3e50;
        }

        p {
            line-height: 1.6;
            font-size: 18px;
            color: #333;
        }

        strong {
            color: #20b2aa;
        }

        em {
            font-style: italic;
            color: #34495e;
        }

        /* Home page background */
        #home {
            background-image: url('./images/fruit_veggie_pic.jpg');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            min-height: 100vh;
        }
        
        #home .container {
            background-color: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(5px);
        }

        /* Food donors page background */
        #donors {
            background-image: url(' ./images/background1.png');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            min-height: 70vh;
            position: relative;
        }
        
        #donors .donors-content {
            display: flex;
            gap: 30px;
            padding: 20px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        #donors .form-container {
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(5px);
            position: relative;
            z-index: 3;
            flex: 1;
            max-width: 900px;
            margin: 0 auto;
        }
        
        #donors .info-box {
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(5px);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            flex: 1;
            max-width: 500px;
            align-self: flex-start;
            margin-top: 60px;
            position: relative;
            z-index: 3;
        }
        
        #donors .info-box h2 {
            color: #2e7d32;
            font-size: 28px;
            margin-bottom: 20px;
            font-weight: 600;
        }
        
        #donors .info-box p {
            color: #555;
            font-size: 16px;
            line-height: 1.6;
        }
        

        
        #donors .donors-tab-header {
            background-color: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(5px);
            position: relative;
            z-index: 3;
        }
        
        /* Food seekers page background */
        #seekers {
            background: linear-gradient(135deg, #a8d5a8 0%, #7cb07c 100%);
            min-height: 70vh;
            position: relative;
        }
        
        #seekers .form-container {
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(5px);
            position: relative;
            z-index: 3;
        }
        
        /* Available donated food page background */
        #donations {
            background: linear-gradient(135deg, #a8d5a8 0%, #7cb07c 100%);
            min-height: 70vh;
            position: relative;
        }
        
        #donations .container, #donations .form-container {
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(5px);
        }
        
        /* Chatbot page background */
        #assistant {
            background: linear-gradient(135deg, #a8d5a8 0%, #7cb07c 100%);
            min-height: 70vh;
            position: relative;
        }
        
        #assistant .form-container {
            background-color: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(5px);
            position: relative;
            z-index: 3;
            max-width: 100%;
            margin: 0;
            padding: 20px;
        }
        
        #assistant .container {
            max-width: 100%;
            margin: 0;
            padding: 20px;
        }

    </style>
</head>
<body>

<header>
    <div style="display: flex; justify-content: center; align-items: center; width: 100%; gap: 60px;">
        <div style="text-align: center;">
            <h1 style="margin: 0;">FoodNearU</h1>
            <p style="margin: 0; color: #ecf0f1; font-size: 18px;">An AI-powered Food Sharing Platform.</p>
        </div>
        <img src="./images/foodnearulogo.jpg" alt="FoodNearU Logo" style="width: 70px; height: 65px; background-color: #2e7d32; padding: 5px; border-radius: 8px;">
    </div>
    <a href="#" class="login-link">Login</a>
</header>

<nav>
    <a href="#" id="home-link">Home</a>
    <a href="#" id="donors-link">Food Donors</a>
    <a href="#" id="seekers-link">Food Seekers</a>
    <a href="#" id="donations-link">Available Donated Food</a>
    <a href="#" id="assistant-link">FoodNearU Chatbot</a>
</nav>

<!-- Home Tab -->
<div id="home" class="tab-content">
    <div class="container">
        <h2>What is FoodNearU's mission?</h2>
        <p>
            Did you know that nearly 733 million people go hungry every day, despite the world producing enough food to feed over 8 billion? Every single day, more than 1 billion meals are wasted, which could nourish those in desperate need.
        </p>
        <p>
            <strong>FoodNearU</strong> is working to change that. We're building a digital platform that connects individuals, restaurants, farms, and other food providers with people facing hunger—making it easy to donate surplus food instead of throwing it away.
        </p>
        <p>
            Together, we can reduce food waste and help feed the world, bringing us a step closer to achieving United Nations' goal 2: <em>Zero Hunger</em>.
        <h2> How does it work? </h2>
        <p>
            In the <strong>food donors</strong> section, users can easily donate canned food, cooked food, purchased food (from restaurants or stores), and produce. If they want to donate cooked food, they have to upload a picture of their license which will be verfied by AI. Afterwards, the user will enter details about their food, such as serving size, cuisine, dietary restrictions, etc. There is also an option for the users to check their award points, which they will earn after donating food.
        </p>
        <p>
            In the <strong>food seekers</strong> section, users can enter their location, a mile range in which they want to search for available food, and any dietary restrictions that they have. Then, it will search for food based on their input and give them a list of options to choose from.
        </p>
    </div>
</div>

<!-- Food Donors Tab -->
<div id="donors" class="tab-content">
    
    <div class="donors-tab-header">
        <a href="#" class="status-link">Change Status of Donated Food</a>
        <a href="#" class="award-points-link">Check My Award Points</a>
    </div>
    
    <div class="donors-content">
        <div class="form-container">
            <h2>Food Donors</h2>
            <h3>Enter Food Details</h3>
            <form id="donor-form">
            <div class="form-group">
                <label for="donor-location">Location where food is available</label>
                <input type="text" id="donor-location" name="donor-location" required placeholder="Enter your location" />
            </div>
            <div class="form-group">
                <label for="food-type">Food Type</label>
                <select id="food-type" name="food-type" required>
                    <option value="">Select Food Type</option>
                    <option value="Cooked Food at my facility">Cooked Food at my facility</option>
                    <option value="Purchased cooked food">Purchased cooked food</option>
                    <option value="Canned Food">Canned Food</option>
                    <option value="Produce">Produce</option>
                </select>
            </div>
            <div class="form-group" id="license-section" style="display: none;">
                <h3>Check my License</h3>
                <p>Upload your license in order to donate cooked food</p>
                <label for="license-upload">Upload License</label>
                <input type="file" id="license-upload" name="license-upload" accept=".pdf,.jpg,.jpeg,.png" />
                <button type="button" id="verify-license" style="margin-top: 10px;">Verify License</button>
            </div>
            <div class="form-group">
                <label for="cuisine">Cuisine</label>
                <select id="cuisine" name="cuisine" required>
                    <option value="Italian">Italian</option>
                    <option value="Indian">Indian</option>
                    <option value="Chinese">Chinese</option>
                    <option value="American">American</option>
                    <option value="Mexican">Mexican</option>
                    <option value="Other">Other</option>
                </select>
            </div>
            <div class="form-group">
                <label for="dietary-restrictions">Vegetarian?</label>
                <select id="dietary-restrictions" name="dietary-restrictions" required>
                    <option value="yes">Yes</option>
                    <option value="no">No</option>
                </select>
            </div>
            <div class="form-group">
                <label for="food-description">Food Description</label>
                <textarea id="food-description" name="food-description" rows="4" required></textarea>
            </div>
            <div class="form-group">
                <label for="serving-size">Serving Size</label>
                <input type="number" id="serving-size" name="serving-size" required />
            </div>
            <div class="form-group">
                <label for="food-picture">Upload Picture of Food</label>
                <input type="file" id="food-picture" name="food-picture" accept=".jpg,.jpeg,.png" />
            </div>
            <button type="submit">Submit Food</button>
        </form>
    </div>
    

    
    </div>
</div>

<!-- Food Seekers Tab -->
<div id="seekers" class="tab-content">
    <div class="form-container">
        <h2>Find Available Food Nearby</h2>
        <div class="form-group">
            <label for="seeker-location">Enter Your Location</label>
            <input type="text" id="seeker-location" placeholder="e.g., 123 Main St" required />
        </div>
        <div class="form-group">
            <label for="seeker-distance">How many miles away?</label>
            <input type="number" id="seeker-distance" value="1" required />
        </div>
        <div class="form-group">
            <label for="dietary-restrictions">Vegetarian?</label>
            <select id="seeker-dietary-restrictions" required>
                <option value="yes">Yes</option>
                <option value="no">No</option>
            </select>
        </div>
        <div class="form-group">
            <button type="button" id="search-food-btn" onclick="searchAvailableFood()">Search for Food Nearby</button>
        </div>
        <div class="form-group">
            <label>Available Food Options</label>
            <table id="food-options-table" style="width: 100%; border-collapse: collapse; margin-top: 10px;">
                <thead>
                    <tr style="background-color: #2e7d32; color: white;">
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Location</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Food Description</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Distance</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Nutritional Value</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Vegetarian?</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Cuisine</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Serving Size</th>
                    </tr>
                </thead>
                <tbody id="food-options-tbody">
                    <tr>
                        <td style="border: 1px solid #ddd; padding: 10px;" colspan="3">Click "Search for Available Food" to find food options near you.</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</div>

<!-- List all Donations Tab -->
<div id="donations" class="tab-content">
    <div class="form-container">
        <h2>Available Donated Food</h2>
        <div class="form-group">
            <label>Available Donated Food</label>
            <table id="donations-table" style="width: 100%; border-collapse: collapse; margin-top: 10px;">
                <thead>
                    <tr style="background-color: #2e7d32; color: white;">
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Location</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Food Description</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Vegetarian?</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Cuisine</th>
                        <th style="border: 1px solid #ddd; padding: 10px; text-align: left;">Serving Size</th>
                    </tr>
                </thead>
                <tbody id="donations-tbody">
                    <tr>
                        <td style="border: 1px solid #ddd; padding: 10px;" colspan="2">No donations available yet.</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</div>

<!-- FoodNearU Chatbot Tab -->
<div id="assistant" class="tab-content">
    <div class="chatbot">
        <h2>FoodNearU Chatbot</h2>
        <div class="chat-box" id="chat-box"></div>
        <input type="text" id="chat-input" placeholder="Enter your question..." />
        <button id="chat-send" onclick="sendAIQuestion(document.getElementById('chat-input').value)">Send</button>
    </div>
</div>

<script>
    // Tab switching
    const homeLink = document.getElementById('home-link');
    const donorsLink = document.getElementById('donors-link');
    const seekersLink = document.getElementById('seekers-link');
    const donationsLink = document.getElementById('donations-link');
    const assistantLink = document.getElementById('assistant-link');
    const homeTab = document.getElementById('home');
    const donorsTab = document.getElementById('donors');
    const seekersTab = document.getElementById('seekers');
    const donationsTab = document.getElementById('donations');
    const assistantTab = document.getElementById('assistant');

    homeLink.addEventListener('click', () => {
        homeTab.classList.add('active');
        donorsTab.classList.remove('active');
        seekersTab.classList.remove('active');
        donationsTab.classList.remove('active');
        assistantTab.classList.remove('active');
    });

    donorsLink.addEventListener('click', () => {
        donorsTab.classList.add('active');
        homeTab.classList.remove('active');
        seekersTab.classList.remove('active');
        donationsTab.classList.remove('active');
        assistantTab.classList.remove('active');
    });

    seekersLink.addEventListener('click', () => {
        seekersTab.classList.add('active');
        homeTab.classList.remove('active');
        donorsTab.classList.remove('active');
        donationsTab.classList.remove('active');
        assistantTab.classList.remove('active');
    });

    donationsLink.addEventListener('click', () => {
        donationsTab.classList.add('active');
        homeTab.classList.remove('active');
        donorsTab.classList.remove('active');
        seekersTab.classList.remove('active');
        assistantTab.classList.remove('active');
        
        // Update the donations table when tab is clicked
        updateDonationsTable();
    });

    assistantLink.addEventListener('click', () => {
        assistantTab.classList.add('active');
        homeTab.classList.remove('active');
        donorsTab.classList.remove('active');
        seekersTab.classList.remove('active');
        donationsTab.classList.remove('active');
    });

    // Default tab (Home is now the first tab)
    homeTab.classList.add('active');

    // Handle food type dropdown change
    const foodTypeSelect = document.getElementById('food-type');
    const licenseSection = document.getElementById('license-section');
    
    foodTypeSelect.addEventListener('change', function() {
        if (this.value === 'Cooked Food at my facility') {
            licenseSection.style.display = 'block';
        } else {
            licenseSection.style.display = 'none';
        }
    });

    // Array to store food donations
    let foodDonations = [];

    // Food data object with required fields
    let fooddata = {
        location: '',
        latitude: '',
        longitude: '',
        foodDescription: '',
        dietryRestrictions: '',
        cuisine: '',
        servingSize: ''
    };

    // Function to geocode address using OpenStreetMap
    async function geocodeAddress(address) {
        const url = `https://nominatim.openstreetmap.org/search?q=${encodeURIComponent(address)}&format=json&limit=1`;

        try {
            const response = await fetch(url, {
                method: 'GET',
                headers: {
                    "User-Agent": "FoodNearU/1.0"
                }
            });

            if (!response.ok) {
                throw new Error(`HTTP error! status: ${response.status}`);
            }

            const data = await response.json();

            if (data && data.length > 0) {
                return {
                    lat: parseFloat(data[0].lat),
                    lon: parseFloat(data[0].lon)
                };
            } else {
                // If no results, try a fallback - just use some default coordinates
                console.warn('Address not found, using default coordinates');
                return {
                    lat: 40.7128,  // NYC coordinates as fallback
                    lon: -74.0060
                };
            }
        } catch (error) {
            console.error('Geocoding failed:', error);
            // Return default coordinates instead of throwing error
            return {
                lat: 40.7128,  // NYC coordinates as fallback
                lon: -74.0060
            };
        }
    }

    // Handle form submission
    const donorForm = document.getElementById('donor-form');
    donorForm.addEventListener('submit', async function(e) {
        e.preventDefault(); // Prevent default form submission
        
        const location = document.getElementById('donor-location').value;
        const foodDescription = document.getElementById('food-description').value;
        const dietryRestrictions = document.getElementById('dietary-restrictions').value;
        const cuisine = document.getElementById('cuisine').value;
        const servingSize = document.getElementById('serving-size').value;
        if (location && foodDescription) {
            try {
                // Show loading message
                
                
                // Get coordinates for the address
                const coordinates = await geocodeAddress(location);
                
                //reinitialize fooddata object  
                fooddata = {
                    location: '',
                    latitude: '',
                    longitude: '',
                    foodDescription: '',
                    dietryRestrictions: '',
                    cuisine: '',
                    servingSize: ''
                };

                
                // Populate fooddata object
                fooddata.location = location;
                fooddata.latitude = coordinates.lat;
                fooddata.longitude = coordinates.lon;
                fooddata.foodDescription = foodDescription;
                fooddata.dietryRestrictions = dietryRestrictions;
                fooddata.cuisine = cuisine;
                fooddata.servingSize = servingSize;
                // Also save to the existing dictionary
                foodDonations.push(fooddata);
                
                console.log('Food data saved:', fooddata);
                console.log('Food donations array:', foodDonations);
                
                // Display the object data to the user
                const displayData = `Food Donation Submitted Successfully!\n\nFood Data:\n` +
                    `Location: ${fooddata.location}\n` +
                    `Latitude: ${fooddata.latitude}\n` +
                    `Longitude: ${fooddata.longitude}\n` +
                    `Food Description: ${fooddata.foodDescription}`;
                
                alert("Submitted Successfully");
                
                // Optional: Reset form
                donorForm.reset();
                
            } catch (error) {
                console.error('Error:', error);
                alert('Error processing location: ' + error.message);
            }
        } else {
            alert('Please fill in both location and food description.');
        }
    });

    // Function to call Gemini API for health status
    async function getHealthStatus(foodName) {
        try {
            const response = await fetch('https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'X-goog-api-key': 'AIzaSyCxkT3zO4R64VCQPt2Vy1nfI2M_2UiaM7U'
                },
                body: JSON.stringify({
                    "contents": [
                        {
                            "parts": [
                                {
                                    "text": `You are an AI Assistant, your job is to choose one option whether given food is healthy, unhealthy or ok to eat and  provide summary in not more than 1 senetnce. For example Burger is not so healthy food, Apple is healthy. So, now tell me whether ${foodName} is healthy or not`
                                }
                            ]
                        }
                    ]
                })
            });

            const data = await response.json();
            if (data.candidates && data.candidates[0] && data.candidates[0].content && data.candidates[0].content.parts && data.candidates[0].content.parts[0]) {
                return data.candidates[0].content.parts[0].text;
            }
            return 'Unknown';
        } catch (error) {
            console.error('Error calling API:', error);
            return 'Error';
        }
    }

    // Function to search for available food using Gemini API
    async function searchAvailableFood() {
        const userLocation = document.getElementById('seeker-location').value;
        seekerCoordinates = await geocodeAddress(userLocation);
        const dietryRestrictions = document.getElementById('seeker-dietary-restrictions').value;
        const mileRange = document.getElementById('seeker-distance').value;
        

        seekerLatitude = seekerCoordinates.lat;
        seekerLongitude = seekerCoordinates.lon;
        if (!userLocation) {
            alert('Please enter your location first.');
            return;
        }

        // Show loading message
        const tbody = document.getElementById('food-options-tbody');
        tbody.innerHTML = '<tr><td style="border: 1px solid #ddd; padding: 10px;" colspan="3">Searching for available food...</td></tr>';
        let availableFoods = [];

        try {
            // Check if there's any food data available
            if (foodDonations.length === 0) {
                tbody.innerHTML = '<tr><td style="border: 1px solid #ddd; padding: 10px;" colspan="3">No food donations available. Please check back later.</td></tr>';
                return;
            }
    
            // Check each donation for distance and dietary match
            await Promise.all(foodDonations.map(async (donation, index) => {
                // Handle undefined dietary restrictions
                const donationDietryRestrictions = donation.dietryRestrictions || 'no';
                const seekerDietryRestrictions = dietryRestrictions || 'no';
                
                
                
                // Check if dietary restrictions match
                if(donationDietryRestrictions === seekerDietryRestrictions){
                    const foodDataString = `Food ${index + 1}: location-${donation.location}, Latitude is ${donation.latitude}, longitude is ${donation.longitude}, food description is ${donation.foodDescription}. `;
                    
                    // Call Gemini API to find distance
                    const response = await fetch('https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent', {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                            'X-goog-api-key': 'AIzaSyCxkT3zO4R64VCQPt2Vy1nfI2M_2UiaM7U'
                        },
                        body: JSON.stringify({
                            "contents": [
                                {
                                    "parts": [
                                        {
                                            "text": `You are an AI Assistant, your job is to give distance between seeker's latitude and longitude 
                                            and fooddata's latitude and longitude. Give the distance in miles.
                                            The fooddata is as follows: ${foodDataString} 
                                            Seeker's latitude is  ${seekerLatitude} and longitude is ${seekerLongitude}. 
                                            Give distance in miles, do not include any explanation or distance unit.
                                            distance should be in float format.
                                            ### Output Format 
                                            ## distance:
                                            For example output should be like this:
                                            {"distance": 1.23}`
                                        }
                                    ]
                                }
                            ]
                        })
                    });

                    const data = await response.json();
            
                    if (data.candidates && data.candidates[0] && data.candidates[0].content && data.candidates[0].content.parts && data.candidates[0].content.parts[0]) {
                        const apiResponse = data.candidates[0].content.parts[0].text;
                       

                        // Parse the JSON response to extract distance
                        let parsedResponse;
                        let distance = null;
                        
                        try {
                            // Clean response if it has extra formatting
                            let cleanResponse = apiResponse.trim();
                            if (cleanResponse.includes('```json')) {
                                cleanResponse = cleanResponse.replace(/```json|```/g, '').trim();
                            }
                            
                            parsedResponse = JSON.parse(cleanResponse);
                            distance = parsedResponse.distance;
                        } catch (e) {
                            console.error('Failed to parse API response:', e);
                            console.log('Raw response:', apiResponse);
                        }
                        
                        // Check if food is within range
                        if (distance !== null && distance <= mileRange) {
                            // Create new object for each food item
                            const availableFood = {
                                location: donation.location,
                                foodDescription: donation.foodDescription,   
                                dietryRestrictions: donationDietryRestrictions,
                                cuisine: donation.cuisine || 'Not specified',
                                servingSize: donation.servingSize || 'Not specified',
                                distance: distance + ' miles'
                            };
                            availableFoods.push(availableFood);
                        
                        } else if (distance !== null) {
                            console.log(`Food at ${donation.location} is ${distance} miles away - too far`);
                        } else {
                            console.log('Failed to get distance for:', donation.location);
                        }
                    }
                }
             }));
             
             // Show message if no food is available within range
             if (availableFoods.length === 0) {
                                   tbody.innerHTML = `<tr><td style="border: 1px solid #ddd; padding: 10px;" colspan="6">No food available within ${mileRange} miles of your location.</td></tr>`;
             } else {
                 populateFoodTable(availableFoods);
             }
            
        } catch (error) {
            console.error('Error searching for food:', error);
            tbody.innerHTML = '<tr><td style="border: 1px solid #ddd; padding: 10px;" colspan="3">Error searching for food. Please try again.</td></tr>';
        }    
            
    }

    async function sendAIQuestion(userQuestion) {
        const userLocation = document.getElementById('seeker-location').value;
        
        // Show loading message
        const tbody = document.getElementById('chat-box');
        tbody.innerHTML = '<div>Processing your question...</div>';
       


        try {
            // Build fooddata string from all donations
            let foodDataString = '';
            foodDonations.forEach((donation, index) => {
                foodDataString += `Food ${index + 1}: location-${donation.location}, food description is ${donation.foodDescription}. `;
            });
            

            // Call Gemini API to find available food using all fooddata
            const response = await fetch('https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'X-goog-api-key': 'AIzaSyCxkT3zO4R64VCQPt2Vy1nfI2M_2UiaM7U'
                },
                    //todo:: give ai to put output in fixed json
                body: JSON.stringify({
                    "contents": [
                        {
                            "parts": [
                                {
                                    "text": `You are an AI Assistant, your job is to answer the question asked by the user about the FoodNearU platform and freeFood available on FoodNearU Platform.
                                    Here are the freeFood available on FoodNearU Platform: ${foodDataString}
                                    Here is the question asked by the user: ${userQuestion}
                                    Here are the details about FoodNearU platform:
                                    Did you know that nearly 733 million people go hungry every day, despite the world producing enough food to feed over 8 billion? Every single day, more than 1 billion meals are wasted, which could nourish those in desperate need. FoodNearU is working to change that. We're building a digital platform that connects individuals, restaurants, farms, and other food providers with people facing hunger—making it easy to donate surplus food instead of throwing it away. Together, we can reduce food waste and help feed the world, bringing us a step closer to achieving UN goal 2: Zero Hunger. In the food donors section, users can easily donate canned food, cooked food, purchased food (from restaurants or stores), and produce. If they want to donate cooked food, they have to upload a picture of their license which will be verfied by AI. Afterwards, the user will enter details about their food, such as serving size, cuisine, dietary restrictions, etc. There is also an option for the users to check their award points, which they will earn after donating food.In the food seekers section, users can enter their location, a mile range in which they want to search for available food, and any dietary restrictions that they have. Then, it will search for food based on their input and give them a list of options to choose from. Also in the food seekers tab, it tells the user whether the available food is healthy or not and a short description of why. `    
                                 }
                            ]
                        }
                    ]
                })
                });

                const data = await response.json();
                if (data.candidates && data.candidates[0] && data.candidates[0].content && data.candidates[0].content.parts && data.candidates[0].content.parts[0]) {
                    
                    const apiResponse = data.candidates[0].content.parts[0].text;
                    tbody.innerHTML = apiResponse;
                }
        
                else {
                    tbody.innerHTML = '<div>No food data available.</div>';
                  }
                } catch (error) {
                 console.error('Error ', error);
                 tbody.innerHTML = '<div>Error processing your question. Please try again.</div>';
        }    
            
    }
 

    // Function to populate the food table with API results
    async function populateFoodTable(availableFoods) {
        const tbody = document.getElementById('food-options-tbody');
        
        // Build table rows for all available food items
        let tableRows = '';
        
        for (const donation of availableFoods) {
            // Check if this donation is mentioned in the API response (meaning it's available)
            const healthStatus = await getHealthStatus(donation.foodDescription);
            
            // Handle vegetarian field - ensure it shows yes/no
            const vegetarianStatus = donation.dietryRestrictions || 'no';
            
            tableRows += '<tr>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.location + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.foodDescription + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.distance + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + healthStatus + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + vegetarianStatus + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.cuisine + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.servingSize + '</td>' +
                '</tr>';
        }
        
        // If no rows were created, show no food available message
        if (tableRows === '') {
            tbody.innerHTML = '<tr><td style="border: 1px solid #ddd; padding: 10px;" colspan="3">No food available in your area.</td></tr>';
        } else {
            tbody.innerHTML = tableRows;
        }
    }

    // Function to update the donations table
    function updateDonationsTable() {
        const tbody = document.getElementById('donations-tbody');
        
        if (foodDonations.length === 0) {
            tbody.innerHTML = '<tr><td style="border: 1px solid #ddd; padding: 10px;" colspan="2">No donations available yet.</td></tr>';
            return;
        }
        
        let tableRows = '';
        foodDonations.forEach((donation, index) => {
            // Handle vegetarian field - ensure it shows yes/no
            const vegetarianStatus = donation.dietryRestrictions || 'no';
            
            tableRows += '<tr>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.location + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.foodDescription + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + vegetarianStatus + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.cuisine + '</td>' +
                '<td style="border: 1px solid #ddd; padding: 10px;">' + donation.servingSize + '</td>' +
                '</tr>';
        });
        
        tbody.innerHTML = tableRows;
    }

</script>

</body>
</html>
