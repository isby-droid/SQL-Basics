SELECT *
FROM crime_scene_report
WHERE type = "murder"
    AND date = "20180115"
    AND city = "SQL City";

SELECT *
FROM person
WHERE address_street_name = "Northwestern Dr"
ORDER BY address_number DESC;

SELECT *
FROM person
WHERE name LIKE '%Annabel%'
    AND address_street_name = "Franklin Ave";

SELECT *
FROM interview
WHERE person_id IN ("14887", "16371");

SELECT *
FROM get_fit_now_check_in
WHERE membership_id LIKE '48Z%'
    AND check_in_date = "20180109";

SELECT *
FROM drivers_license
WHERE gender = "male"
    AND plate_number LIKE '%H42W%';

SELECT *
FROM person
WHERE license_id IN ("423327", "664760");

SELECT *
FROM get_fit_now_member
WHERE person_id IN ("51739", "67318");

![image](https://github.com/user-attachments/assets/9fafbc8f-d614-42c2-ae2d-69e06a713b99)


SELECT *
FROM interview
WHERE person_id = "67318";

SELECT *
FROM drivers_license
WHERE gender = "female"
    AND hair_color = "red"
    AND height BETWEEN 65 AND 67
    AND car_make = "Tesla"
    AND car_model = "Model S";

SELECT *
FROM person
WHERE license_id IN ("202298", "291182", "918773");

SELECT 
    person_id, 
    event_name, 
    COUNT(*) AS event_count
FROM facebook_event_checkin
WHERE person_id IN ("78881", "90700", "99716")
GROUP BY person_id, event_name;

![image](https://github.com/user-attachments/assets/85cfe1ca-6287-46d9-835d-da5d20cf6e73)

