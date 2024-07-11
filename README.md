Project Title: SQL Murder Mystery Project

Overview

This project demonstrates my SQL skills through a fictional crime investigation. The challenge involves assisting a detective by retrieving and analyzing data from a police department's database to solve a murder mystery.

Project Description

A murder occurred on January 15, 2018, in SQL City. The detective needs our help to retrieve the crime scene report and follow the data trail to identify the murderer and who hired them.

Steps and Methods

Retrieving Crime Scene Report:

Objective: Find the crime scene report for the murder that occurred on January 15, 2018, in SQL City. Query:

SELECT * FROM crime_scene_report WHERE date = '2018-01-15' AND city = 'SQL City' AND type = 'murder'; Results: The report indicated there were two witnesses: one at the last house on "Northwestern Dr" and another named Annabel on "Franklin Ave." Identifying Witnesses:

Objective: Retrieve details of the witnesses from the person table. Queries:

SELECT * FROM person
WHERE address_street_name LIKE '%Northwestern Dr%' ORDER BY address_number DESC LIMIT 1;

SELECT * FROM person WHERE name LIKE '%Annabel%' AND address_street_name = 'Franklin Ave'; Results: Witnesses identified as Morty Schapiro and Annabel Miller. Retrieving Witness Interviews:

Objective: Check the transcripts of the witnesses' interviews. Query:

SELECT * FROM interview i JOIN person p ON i.person_id = p.id WHERE p.name IN ('Morty Schapiro', 'Annabel Miller'); Results: Witnesses reported seeing a man with a "Get Fit Now Gym" bag and a car with a plate number including "H42W." Identifying the Suspect:

Objective: Use the gym membership information to trace the suspect. Query:

SELECT * FROM get_fit_now_member WHERE id LIKE '48Z%' AND membership_status = 'gold'; Results: Potential suspects identified as Joe Germuska and Jeremy Bowers. Narrowing Down the Suspect:

Objective: Match the car plate number "H42W" with the driver's license records. Query:

SELECT * FROM person p JOIN drivers_license d ON p.license_id = d.id WHERE plate_number LIKE '%H42W%'; Results: Jeremy Bowers matched the description and the car plate number. Finding the Employer:

Objective: Determine who hired Jeremy Bowers. Query:

SELECT * FROM interview WHERE person_id = 67318; Results: Jeremy Bowers was hired by a woman with red hair, 5'5" to 5'7" tall, driving a Tesla Model S, who attended the SQL Symphony Concert three times in December 2017. Identifying the Employer:

Objective: Find the woman matching the description. Query:

SELECT * FROM person p JOIN drivers_license d ON p.license_id = d.id WHERE gender = 'female' AND hair_color = 'red' AND car_make = 'Tesla' AND car_model = 'Model S'; Results: Potential suspects identified as Red Corb, Reginal George, and Miranda Priestly. Confirming the Employer:

Objective: Check event attendance to confirm the suspect. Query:

SELECT p.name FROM person p JOIN facebook_event_checkin f ON p.id = f.person_id WHERE f.person_id IN (78881, 90700, 99716) AND f.event_name = 'SQL Symphony Concert' AND f.date LIKE '201712%'; Results: Miranda Priestly attended the SQL Symphony Concert in December 2017.

Conclusion The investigation concludes that Miranda Priestly hired Jeremy Bowers to commit the murder. This project demonstrates the application of SQL in solving complex, real-world problems by systematically analyzing and querying data.

How you can help me:

I've successfully completed other projects, all showcased in my portfolio. You're all invited to visit my portfolio @https://olayimikatimileyin.github.io/Mickey-github.io/

 and explore these amazing projects!

Additionally, I'm currently seeking internship or entry-level opportunities. If you have any opportunities available, please connect with me on LinkedIn.

Looking forward to connecting with you all!

Created and Presented by- Akinbowale Micheal @Aspiring Data Analyst @https://www.linkedin.com/in/akinbowale-micheal/

Location: Nigeria

THE END
