# Lab 1

# Exercise 1

## Task: Add a new rule to the Knowledge Base for students who have a CGPA of 3.70 or higher and zero disciplinary warnings.

# Exercise 1: Degree Honors Rule

UNIVERSITY_KB["rules"].append({
    "id": "RULE_07",
    "conditions": {
        "cgpa_min": 3.70,
        "disciplinary_warnings": 0
    },
    "condition_type": "degree_honors",
    "status": "Graduated with Magna Cum Laude Honors",
    "action": "Eligible for Degree Honors."
})

print("New Degree Honors Rule Added Successfully!")
