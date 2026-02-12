# Travel Planner Web Application

A minimalistic, feature-rich travel planning application that helps you plan your perfect road trip with route optimization, cost calculation, and discovery of points of interest and accommodations along your route.

## Features

### 🗺️ Route Planning
- **Origin & Destination Input** with Google Places autocomplete
- **Multiple Waypoints** for complex multi-stop trips
- **Route Optimization** with three modes:
  - Fastest route
  - Shortest route
  - Scenic route (avoids highways)
- **Interactive Map** with turn-by-turn directions visualization

### 💰 Cost Calculator
- **Real-time Distance Calculation** in miles or kilometers
- **Fuel Efficiency Options**:
  - MPG (Miles Per Gallon)
  - L/100km (Liters per 100 kilometers)
- **Custom Fuel Price Input**
- **Automatic Cost Estimation** including:
  - Total trip distance
  - Estimated fuel consumption
  - Total fuel cost

### 📍 Points of Interest
- **Automatic Discovery** of attractions along your route
- **Filter Options**:
  - All types
  - Restaurants & Cafes
  - Gas Stations
  - Scenic Viewpoints & Parks
  - Tourist Attractions & Museums
- **Detailed Information**:
  - Location name and address
  - Star ratings
  - Number of reviews

### 🏨 Accommodation Finder
- **Hotel Discovery** near your route
- **Smart Filtering**:
  - Price range (Budget, Mid-range, Luxury)
  - Minimum rating (3+, 4+, 4.5+)
- **Comprehensive Details**:
  - Name and location
  - Price level indicators
  - Guest ratings

### 💾 Smart Features
- **Local Storage** saves your fuel preferences automatically
- **Collapsible Sections** to reduce interface clutter
- **Responsive Design** works perfectly on desktop and mobile
- **Fast Loading** with optimized code and lazy loading

## Getting Started

### Prerequisites

You'll need:
1. A Google Maps API key with the following APIs enabled:
   - Maps JavaScript API
   - Places API
   - Directions API

### Getting Your Google Maps API Key

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Enable the required APIs:
   - Go to "APIs & Services" > "Library"
   - Search for and enable:
     - Maps JavaScript API
     - Places API
     - Directions API
4. Go to "APIs & Services" > "Credentials"
5. Click "Create Credentials" > "API Key"
6. Copy your API key

### Installation

1. **Download the Files**
   - Download `travel-planner.html` to your computer

2. **Add Your API Key**
   - Open `travel-planner.html` in a text editor
   - Find the line near the bottom that says:
     ```html
     <script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&libraries=places&callback=initMap" async defer></script>
     ```
   - Replace `YOUR_API_KEY` with your actual Google Maps API key

3. **Open the Application**
   - Simply open the HTML file in any modern web browser (Chrome, Firefox, Safari, Edge)
   - No web server required!

## How to Use

### Planning Your Trip

1. **Enter Your Route**
   - Type your starting location in the "Origin" field
   - Type your destination in the "Destination" field
   - (Optional) Click "Add Waypoint" to add stops along the way
   - (Optional) Select a travel date

2. **Choose Route Type**
   - **Fastest**: Optimized for time, may use highways
   - **Shortest**: Minimizes distance
   - **Scenic**: Avoids highways for a more scenic drive

3. **Click "Plan Route"**
   - The map will display your route
   - Statistics will automatically calculate

### Calculating Trip Costs

1. **Configure Your Vehicle**
   - Select distance unit (Miles or Kilometers)
   - Select fuel unit (MPG or L/100km)
   - Enter your vehicle's fuel efficiency
   - Enter current fuel price in your area

2. **View Results**
   - Total distance
   - Estimated fuel needed
   - Estimated fuel cost

### Discovering Places

1. **Points of Interest**
   - Automatically populated after route calculation
   - Use the filter dropdown to see specific types
   - Expand/collapse the section using the header

2. **Accommodations**
   - Filter by price range (Budget/Mid-range/Luxury)
   - Filter by minimum rating
   - View hotels, motels, and lodging along your route

## Technical Details

### Technology Stack
- **Pure HTML/CSS/JavaScript** - No frameworks required
- **Google Maps JavaScript API** - For mapping and places
- **Local Storage API** - For saving user preferences
- **Responsive CSS Grid** - For mobile-friendly layout

### Browser Compatibility
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

### Performance Features
- **Lazy Loading** of map and places data
- **Efficient API Calls** with result limiting
- **Debouncing** on autocomplete inputs
- **Optimized Rendering** with virtual scrolling for long lists

## Customization

### Changing Default Values

You can modify default values by editing these variables in the HTML:

```javascript
// Default fuel efficiency
document.getElementById('fuelEfficiency').value = 25; // Change to your vehicle's MPG

// Default fuel price
document.getElementById('fuelPrice').value = 3.50; // Change to your local price
```

### Styling

All styles are contained in the `<style>` section. Key customization points:

```css
/* Primary color */
background-color: #4A90E2; /* Change to your preferred color */

/* Card border radius */
border-radius: 12px; /* Adjust for more/less rounded corners */

/* Font family */
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
```

### Adjusting Search Radius

To find more or fewer places along the route:

```javascript
// In the searchNearby function
radius: 5000 // Change this value (in meters)
```

## Troubleshooting

### Map Not Loading
- **Check API Key**: Ensure you've replaced `YOUR_API_KEY` with your actual key
- **Check APIs Enabled**: Verify all required APIs are enabled in Google Cloud Console
- **Check Browser Console**: Press F12 and look for error messages

### No Places Found
- **Route Too Short**: Try a longer route
- **API Limits**: Check if you've exceeded your API quota
- **Filter Too Restrictive**: Try "All" filter instead of specific types

### Cost Calculation Incorrect
- **Check Units**: Ensure you're using the correct fuel efficiency unit
- **Verify Input**: Make sure fuel efficiency and price are entered correctly

### Autocomplete Not Working
- **API Key**: Verify Places API is enabled
- **Browser Permissions**: Some browsers require HTTPS for geolocation

## API Usage and Costs

### Google Maps API Pricing (as of 2026)

- **Maps JavaScript API**: $7 per 1,000 loads
- **Places API**: $17 per 1,000 requests
- **Directions API**: $5 per 1,000 requests

**Monthly Free Credit**: Google provides $200 free credit per month, which covers:
- ~28,000 map loads
- ~11,000 places searches
- ~40,000 directions requests

### Optimizing API Usage

The app is optimized to minimize API calls:
- Places searches are limited to 5 results per location
- Sample points along route (not every point)
- Results are cached during the session
- No API calls made until "Plan Route" is clicked

## Privacy & Data

- **No Data Collection**: This app runs entirely in your browser
- **Local Storage Only**: Preferences saved locally on your device
- **No Server**: No data sent to any server except Google Maps API
- **No Tracking**: No analytics or tracking scripts

## Future Enhancements

Potential features for future versions:
- Weather forecast integration
- Traffic conditions display
- Save/load trip plans
- Share trips via URL
- Print-friendly itinerary
- Alternative transportation modes (walking, cycling, transit)
- Multi-day trip planning
- Offline map support

## Support

For issues related to:
- **Google Maps API**: Visit [Google Maps Platform Support](https://developers.google.com/maps/support)
- **Application Bugs**: Check the browser console for error messages
- **Feature Requests**: Consider forking and modifying the code

## License

This project is provided as-is for personal and educational use. The Google Maps API usage is subject to Google's terms of service.

## Credits

Built with:
- Google Maps JavaScript API
- Google Places API
- Lucide Icons (referenced in comments)
- Modern web standards (HTML5, CSS3, ES6+)

---

**Happy Travels! 🚗✨**

Start planning your next adventure with confidence!