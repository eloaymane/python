# python
trading_bot


import requests
import time
#global variables
api_key = '********'
bot_key = '************'
chat_id = '*******'
limit = 59000
time_interval = 5 * 6
def get_price():
    url = 'https://pro-api.coinmarketcap.com/v1/cryptocurrency/listings/latest'

    headers = {
        'Accepts': 'application/json',
        'X-CMC_PRO_API_KEY': '**********',
    }
    response = requests.get(url, headers=headers).json()
    return response


def send_update(chat_id, msg):
    url =f"https://api.telegram.org/bot{url}/sendMessage?chat_id={******} &text={msg}"
    requests.get(url)

def main():
    while True:
        price = get_price()
        if price < limit:
            send_update(chat_id, f" price *** :{price}")
            time.sleep(time_interval)

main()



#

For setup see this:

https://coinmarketcap.com/api/documentation/v1/#section/Quick-Start-Guide


https://core.telegram.org/bots/api




#
