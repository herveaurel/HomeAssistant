## 2024-02-13

1. error corrections :   
    - color of the badge calendar `bubble` in the `Activity card`  
    - color of the badge bin `bubble` in the `Activity card`  

2. Proximity  
The integration is now in the UI and removed from the YAML configuration.  
The entity names are different.  
    - I created a sensor template for each person: `sensor.proximity_NAME`  
    - I modified the person card to `person_complete_card` 
    - I modified the `proximity` variable in the dashboard card   

---

## 2024-02-14  

- Reduce font-size of the time to avoid text being cut off at the top

---

## 2024-02-15

1. Electric consumption:  

- Creation of two input_number entities for the monthly subscription price and the price per kWh.  
- Modification of the sensor templates to calculate the price, automatically considering the input_number values.  
- Addition of the two input_number entities to the Energy tab.  

2. Persons:

- Removal of the `person_child_card` button card template.  
- Modification of the `person_complete_card` button card template. 
    - Modification of the `gps` custom_fields to now integrate both the `Proximity` and `Waze` integrations into a single button, adapting to the journey to work or home.  
- Modification of the sensor template `sensor.proximity_xxx`.  
- Modification of the sensor template `sensor.xxx_trajet`.  
- Modification of the sensor template `sensor.xxx_gps` for children (I now use the `Apple iCloud integration to locate them because they do not have the Home Assistant app on their phone).  
- Modification of the `variables` in the Person cards on the Person tab.

3. Weather card

- Correction of the units for the sky, rain, and snow sensors.