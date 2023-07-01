# Binance-API
This script uses the Binance API to fetch the current prices of cryptocurrencies
import requests

def get_crypto_price(crypto_symbol):
    url = f'https://api.binance.com/api/v3/ticker/price?symbol={crypto_symbol}USDT'
    response = requests.get(url)
    data = response.json()
    if 'price' in data:
        return float(data['price'])
    return None

# Example usage
crypto_symbols = ['BTC', 'ETH', 'DOGE']
for symbol in crypto_symbols:
    price = get_crypto_price(symbol)
    if price:
        print(f"Current price of {symbol}: ${price}")
    else:
        print(f"Failed to retrieve price for {symbol}")
