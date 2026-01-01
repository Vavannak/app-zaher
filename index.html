import requests
import sys
import time
from bs4 import BeautifulSoup
from flask import Flask, request, jsonify, send_file
from flask_cors import CORS
import io

app = Flask(__name__)
CORS(app) # Fixes the CORS error for the website

# --- FIXED ERROR FINDER LOGIC ---
def scrape_targets(domain, limit=100):
    found_urls = []
    headers = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64)'}
    
    # Example search using Bing (Google often blocks automated requests)
    search_url = f"https://www.bing.com/search?q=site:{domain}&count={limit}"
    
    try:
        response = requests.get(search_url, headers=headers, timeout=10)
        response.raise_for_status() # Fix: Catch HTTP errors
        
        soup = BeautifulSoup(response.text, 'html.parser')
        
        # Fixed finding logic: Look for all <a> tags with hrefs
        for link in soup.find_all('a', href=True):
            url = link['href']
            # Filter for specific domain to ensure quality
            if domain in url and "http" in url and "microsoft" not in url:
                found_urls.append(url)
                
        return list(set(found_urls)) # Remove duplicates
    except Exception as e:
        return {"error": str(e)}

@app.route('/find', methods=['POST'])
def find():
    data = request.json
    domain = data.get('domain')
    limit = data.get('limit', 100)
    
    results = scrape_targets(domain, limit)
    return jsonify(results)

if __name__ == "__main__":
    print("[*] Server running on http://127.0.0.1:5000")
    app.run(debug=True)