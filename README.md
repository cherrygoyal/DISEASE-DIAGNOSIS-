# DISEASE-DIAGNOSIS-
def get_symptom_input(question):
    response = input(question + " (yes/no): ").lower()
    return response == 'yes'

def calculate_pulse():
    # Placeholder function to estimate diabetes level
    return 75 # Assume for demonstration purpose

def calculate_bp():
    # Placeholder function to estimate diabetes level
    systolic = 120
    diastolic = 80
    return systolic, diastolic # Assume for demonstration purpose

def estimate_diabetes_level():
    # Placeholder function to estimate diabetes level
    return "Normal"

def suggest_nearby_doctors(location):
    # Placeholder function to suggest nearby doctors
    # You can integrate with a real database or API
    return ["Dr. A", "Dr. B", "Dr. C"]

def call_ambulance():
    print("Calling ambulance...")

def diagnose_disease():
    print("Welcome to the Disease Detection Program.")
    print("Please answer the following questions with 'yes' or 'no'.\n")

    body_temp = int(input("what is your body temperature in celcius: "))
    fever = get_symptom_input("Do you have a fever?")
    cough = get_symptom_input("Do you have a cough?")
    nose = get_symptom_input("Do you have runny or stuffy nose?")
    cramp = get_symptom_input("Do you have stomach pain and cramps?")
    fatigue = get_symptom_input("Are you experiencing fatigue or weakness?")
    headache = get_symptom_input("Do you have a headache?")
    vomit = get_symptom_input("Do you have any vomit?")
    const = get_symptom_input("Do you have any constipation?")
    sore_throat = get_symptom_input("Do you have a sore throat?")

    pulse_rate = calculate_pulse()
    systolic_bp, diastolic_bp = calculate_bp()
    diabetes_level = estimate_diabetes_level()

    if fever and cough and fatigue:
        if const:
            print("You may have typhoid. Avoid high fibrous food, improve WASH (water and sanitation, hygiene) and consult a doctor.")
        elif headache:
            print("You may have the flu. Please consult a doctor.")
        elif nose and sore_throat:
            print("You may have a common cold. Rest and stay hydrated.")

        else:
            print("You may have a viral infection. Consult a healthcare provider.")
    elif fever and cramp and fatigue and headache and vomit:
        print("You may suffering from food poisioning. Rest, take ORAL hydration and consume fruits.")
    elif fever and headache:
        print("You may have a heat stroke or meningitis. Seek immediate medical attention.")
    elif cough and sore_throat:
        print("You may have bronchitis or a respiratory infection. Consult a doctor.")
    else:
        print("Symptoms are not conclusive. Please consult a healthcare professional for a proper diagnosis.")

    print()
    print(f"Your pulse rate: {pulse_rate} bpm")
    print(f"Blood Pressure (BP): {systolic_bp}/{diastolic_bp} mmHg")
    print(f"Diabetes level: {diabetes_level}")

# Suggest nearby doctors
    user_location = "37.7749,-122.4194"  # Example: San Francisco coordinates
    nearby_doctors = suggest_nearby_doctors(user_location)
    print(f"Nearby doctors: {', '.join(nearby_doctors)}")


# Call ambulance in severe situations
    if pulse_rate > 100 or systolic_bp > 180 or diastolic_bp > 110:
        call_ambulance()
    print()



    print('''Stay Cautious:
1.Clean your hands.
2.Avoid close contact with people.
3.Cover your mouth and nose when coughing or sneezing.
4.Avoid touching your eyes, nose, and mouth with unwashed hands.
5.Stay cool
6.Drink plenty of fluid
7.Take tulsi, coriander, ginger, honey tea
8.Take proper rest''')

# Suggest nearby doctors

import googlemaps
from datetime import datetime

gmaps =googlemaps.Client(key='Add Your Key here')

# Geocoding an address

geocode_result = gmaps.geocode('08, PU04 , Commercial Scheme')
# Look up an address with reverse geocoding

reverse_geocode_result = gmaps.reverse_geocode((40.714224, -73.961452))

# Request directions via public transit

now = datetime.now()
directions_result = "Rasoma square , A.B Road VIjsy Nagar , Indore" , gmaps.directions( mode="transit", departure_time=now)


# Start the diagnosis process
diagnose_disease()

