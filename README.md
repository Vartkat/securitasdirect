# securitasdirect


Home Assistant custom component integrating Securitas Direct (AKA Verisure EU) alarms, based on mobile API (thanks to https://github.com/Cebeerre/VerisureAPIClient great Cebeerre work...)

<img src="https://github.com/segalion/securitasdirect/raw/master/securitas_HA.gif">


## Install HA component
1. Download [securitasdirect zip project](https://github.com/segalion/securitasdirect/archive/master.zip)
2. unzip and just copy 'custom_components' folder inside Home Assistant config folder
3. configure your configuration.yaml with proper securitas_direct/verisure parameters (as [example_config.yaml](https://github.com/segalion/securitasdirect/blob/master/custom_components/securitas_direct/example_config.yaml) )
```
securitas_direct:
  username: your_securitas_username
  password: your_securitas_password
  code: 1234
  country: ES
```
4. Enable track of all your remotes and keys (on mobile app), to get good sync between real Securitas Alarm and the HA alarm component. 
5. restart Home Assistant and search for unused entities. Include it in lovelace frontend (following [documentation](https://www.home-assistant.io/lovelace/alarm-panel/)).

## Standalone
You can use the python command_line tool to interact with Securitas Direct (Verisure EU), withot need Home Assistant (i.e. integrate on other assistants):

1. Download "[securitas.py](https://github.com/segalion/securitasdirect/raw/master/custom_components/securitas_direct/securitas.py)" script file
2. install proper requirements:
`pip3 install requests xml2dict`
3. make it executable 
`chmod +x securitas.py`
4. run with 
`securitas.py username password [ACTION] [COUNTRY_CODE]`

( to see all actions:
`securitas.py username password ?` )

There are an [old cli bash version](https://github.com/segalion/securitasdirect/tree/master/old) to interact with web access

## TODO:
- Photo (CAMERA) request

## NOTES:

This project has no relationship with Securitas Direct / Verisure company (unofficial).

The component emulate the access for this "My Verisure" mobile app.
<img src="https://lh3.googleusercontent.com/MnZWWDdoqVZ69NBTe2YVE5soAxtRIqaEkFazk9wm2Jp2RiJ3eCxzGFBjKxil6RZTPAY=w1291-h663" alt="drawing" width="100"/> 
You have to ensure you can manage your alarm with this app before configure this component in Home Assistant. Even it is designed to make as less as request as possible, please, take into account that company could charge for this access.

Has been tested in Spain. Similar webs has been found in 
- France: https://customers.securitasdirect.fr/
- Italy: https://customers.verisure.it/
- UK: https://customers.verisure.co.uk/
- Portugal: https://customers.securitasdirect.pt/
- Brasil: https://customers.verisure.com.br/
- Netherland: 
- Chile:
- Perú:


You can report ISSUEs about it, and working countries [in issue 8](https://github.com/segalion/securitasdirect/issues/8)

Thanks.

## LICENCE:
Code is under MIT licence.   
