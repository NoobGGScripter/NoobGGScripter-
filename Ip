import requests

def get_ip():
    # Get your public IP address using ipify
    response = requests.get('https://api.ipify.org?format=json').json()
    return response["ip"]

def get_location(ip_address):
    try:
        # Fetch location information using ipapi
        response = requests.get(f'https://ipapi.co/{ip_address}/json/').json()
        location_data = {
            "ip": ip_address,
            "city": response.get("city"),
            "region": response.get("region"),
            "country": response.get("country_name"),
            "currency": response.get("currency"),
            "phone_number": response.get("country_calling_code"),
            "national_format": response.get("languages"),
        }
        return location_data
    except Exception as e:
        print(f"Error retrieving location: {e}")
        return None

if __name__ == "__main__":
    ip_address = input("Enter an IP address: ")  # Example: 117.214.109.137
    location_info = get_location(ip_address)
    if location_info:
        print("Location Details:")
        for key, value in location_info.items():
            print(f"{key.capitalize()}: {value}")
    else:
        print("Invalid IP address or error occurred.")
