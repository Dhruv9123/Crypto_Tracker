# Crypto_Tracker
The provided Python code is a Cryptocurrency Tracker Application built using the Tkinter library for the GUI, along with libraries such as matplotlib for visualizations and pandas for data manipulation. The application fetches cryptocurrency data from the CoinGecko API, allowing users to search, select, track, and visualize cryptocurrency performance.
Key Functionalities:
  1. Fetching and Displaying Data:
      Fetches a list of all cryptocurrencies.
      Allows searching by cryptocurrency name in real-time.
     
  2. Selection and Tracking:
      Enables the selection of cryptocurrencies for tracking.
      Saves and loads selected cryptocurrencies for persistence.
  
  3. Data Visualization:
      Displays historical price trends for selected cryptocurrencies.
      Shows current market metrics like price, 24-hour high/low, and price change.
  
  4. CRUD Operations:
      Allows users to delete selected cryptocurrencies from tracking.

     
Code Structure:
  1. Modules and Imports
      tkinter: Provides the GUI functionality.
      matplotlib: Used for creating performance charts.
      requests: For API calls to fetch cryptocurrency data.
      threading: Loads data asynchronously to prevent freezing the GUI.
      pandas: Manages and manipulates cryptocurrency data.

2. API Functions
  These functions fetch data from CoinGecko's API:
    get_crypto_list: Fetches a complete list of available cryptocurrencies. Returns data as JSON.
    fetch_crypto_data: Fetches current market data for selected cryptocurrencies. Accepts a list of crypto IDs and retrieves attributes like price, market cap, etc.
    fetch_historical_data: Fetches historical price data for the last 7 days. Parses and formats the data into dates and prices.

3. GUI Implementation
  The app is encapsulated within the cryptoTrackerApp class:
    Initialization (__init__): Sets up the GUI elements. Loads cryptocurrency data asynchronously.
    Widgets (create_widgets): Search bar for real-time filtering. Listbox for displaying results. Buttons for selecting, tracking, and deleting cryptocurrencies. Table and charts for visualizations.
    Loading Data: Uses the LoadingPopup class to display a progress bar while fetching data.

4. Core Functionalities
    Searching Cryptocurrencies (update_search_results): Filters cryptocurrencies based on the user-entered search term. Uses a case-insensitive string search.
    Selecting Cryptocurrencies (select_cryptos): Adds selected cryptocurrencies to a tracking list. Saves the selection in a CSV file for persistence.
    Loading Tracked Cryptos (load_selected_cryptos): Reads previously saved data from a CSV file and loads it into the GUI.
    Deleting Cryptos (delete_selected_cryptos): Removes selected cryptocurrencies from the tracking list. Updates the saved CSV file.
    Tracking and Visualization: Fetches historical data for selected cryptocurrencies. Displays price trends and market statistics using matplotlib and a table (Treeview).
  Visualization
  The show_crypto_performance function:
  Creates a new window displaying:
  A table with current market stats (price, high/low, changes).
  A line chart showing 7-day historical price trends.
  Important Notes
    Concurrency: The threading module ensures that data loading happens in a background thread, preventing the GUI from freezing.
    Error Handling: Handles API errors using try-except blocks and ensures resilience in case of network issues.
    File Persistence: Tracks selected cryptocurrencies using a CSV file, allowing the application to restore user preferences across sessions.
  
