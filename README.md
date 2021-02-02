# symptoms-and-disease
class Disease:
     def __init__(self, name, symptoms):
         self.name = name
         self.symptoms = symptoms


known_diseases = [
   Disease('cold', set(
     "sore throat|runny nose|congestion|cough|aches".split("|"))
     ),
   Disease('flu', set(
     "fever|headache|muscle aches|returning fever".split("|"))
     ),
   Disease('ebola', set(
     "tiredness|death|bruising over 90% of body|black blood".split("|"))
     ),
   Disease('Allergies', set(
     "eye irritation|runny nose|stuffy nose|watery eyes|sneezing".split("|"))
     ),
   Disease('diarrhea', set(
     "watery stools|frequent bowel movements|pain in abdomen|nausea|bloating".split("|"))
     ),
   ]


symptoms = input("Please enter symptoms separated by commas: ")
symptoms = symptoms.lower()
symptoms = symptoms.split(",")

possible = []
for symptom in symptoms:
     for disease in known_diseases:
         if symptom in disease.symptoms:
             possible.append(disease.name)

if possible:
     print("You may have these diseases:")
     print(*possible)
else:
     print("Good news! You're going to have a disease named after you!")
