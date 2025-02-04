# DApp List for Web3 DApp Browser

This repository contains a JSON file (`dapp-list.json`) that defines the structure for a bookmark/home screen for a Web3 DApp browser. The file includes:

- **Banners:** A list of banner objects to be shown in a clickable, scrollable banner scroller at the top of the home screen.
- **Featured:** A list of featured DApps/websites that are highlighted at the top of the home screen.
- **Websites:** A flat array of website objects. Each website object includes:
  - `title`: The display name.
  - `url`: The website URL.
  - `icon`: A URL to the website's favicon (or another icon).
  - `categories`: An array of categories. A website can belong to multiple categories (e.g. "nft", "dex", "tools", "games", etc.).
  - `description`: A short description of the website.

## Categories

Some example categories included in this JSON file are:
- **all**
- **nft**
- **dex**
- **tools**
- **games**
- **meme**
- **gaming**
- **staking**
- **bridge**
- **governance**
- **crowdfunding**
- **utilities**

A single website can appear in multiple categories. For example, **OpenSea** is listed under `"nft"` and `"marketplace"`, and it also appears in the `"all"` category.

## Usage

1. **Host the JSON:**  
   Upload `dapp-list.json` to your GitHub repository (or GitHub Gist) so that it’s accessible via a public URL.

2. **Fetch the JSON in Your App:**  
   In your DApp browser app, use `fetch()` (or another HTTP library) to load this JSON file:
   ```js
   fetch("https://raw.githubusercontent.com/yourusername/yourrepo/main/dapp-list.json")
     .then(response => response.json())
     .then(data => {
       // Use the data to populate your home screen:
       // - Display banners in a horizontal scroller
       // - Render featured websites at the top
       // - Group or filter the websites by category
     })
     .catch(error => console.error("Error fetching dapp list:", error));
