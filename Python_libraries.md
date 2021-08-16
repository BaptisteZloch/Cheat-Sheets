- Phone location : phonenumbers
```py
import phonenumbers
number = "+33661500669"

from phonenumbers import geocoder
from phonenumbers import carrier
ch_number = phonenumbers.parse(number,"CH")
service_number = phonenumbers.parse(number,"RO")

print(geocoder.description_for_number(ch_number,"en"))
print(carrier.name_for_number(service_number,"en"))
```