patients = []

while True:
    print("\n===== Hospital Management System =====")
    print("1. Add Patient")
    print("2. View Patients")
    print("3. Search Patient")
    print("4. Delete Patient")
    print("5. Exit")

    choice = int(input("Enter your choice: "))

    if choice == 1:
        pid = input("Patient ID: ")
        name = input("Patient Name: ")
        age = input("Age: ")
        disease = input("Disease: ")

        patients.append({
            "ID": pid,
            "Name": name,
            "Age": age,
            "Disease": disease
        })

        print("Patient Added Successfully!")

    elif choice == 2:
        if len(patients) == 0:
            print("No Patients Found.")
        else:
            for p in patients:
                print("----------------------------")
                print("ID:", p["ID"])
                print("Name:", p["Name"])
                print("Age:", p["Age"])
                print("Disease:", p["Disease"])

    elif choice == 3:
        pid = input("Enter Patient ID: ")
        found = False
        for p in patients:
            if p["ID"] == pid:
                print("----------------------------")
                print("ID:", p["ID"])
                print("Name:", p["Name"])
                print("Age:", p["Age"])
                print("Disease:", p["Disease"])
                found = True
                break
        if not found:
            print("Patient Not Found.")

    elif choice == 4:
        pid = input("Enter Patient ID to Delete: ")
        found = False
        for p in patients:
            if p["ID"] == pid:
                patients.remove(p)
                print("Patient Deleted Successfully!")
                found = True
                break
        if not found:
            print("Patient Not Found.")

    elif choice == 5:
        print("Thank You!")
        break

    else:
        print("Invalid Choice!")
