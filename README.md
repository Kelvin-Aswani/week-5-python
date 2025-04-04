# week-5-python
class Superhero:
    def __init__(self, name, power, secret_identity, weakness):
        self.name = name
        self.power = power
        self.__secret_identity = secret_identity  # Encapsulated attribute
        self.weakness = weakness

    def reveal_identity(self):
        return f"My secret identity is {self.__secret_identity}."

    def use_power(self):
        return f"{self.name} uses {self.power}!"

    def save_civilian(self, civilian_name):
        return f"{self.name} saves {civilian_name} from danger!"

    # Encapsulation: Getter and setter for secret_identity
    @property
    def secret_identity(self):
        return self.__secret_identity

    @secret_identity.setter
    def secret_identity(self, new_identity):
        self.__secret_identity = new_identity

# Subclass: Avenger (inherits from Superhero)
class Avenger(Superhero):
    def __init__(self, name, power, secret_identity, weakness, team):
        super().__init__(name, power, secret_identity, weakness)
        self.team = team

    # Polymorphism: Override use_power method
    def use_power(self):
        return f"{self.name} unleashes {self.power} with the Avengers' style!"

    def introduce(self):
        return f"I am {self.name}, part of the {self.team}!"

# Example Usage
if __name__ == "__main__":
    iron_man = Avenger(
        name="Iron Man", 
        power="repulsor beams", 
        secret_identity="Tony Stark", 
        weakness="battery life", 
        team="Avengers"
    )

    print(iron_man.use_power())  # Output: "Iron Man unleashes repulsor beams with the Avengers' style!"
    print(iron_man.introduce())  # Output: "I am Iron Man, part of the Avengers!"
    print(iron_man.reveal_identity())  # Output: "My secret identity is Tony Stark."



class Vehicle:
    def move(self):
        raise NotImplementedError("Subclasses must define move()!")

class Car(Vehicle):
    def move(self):
        return "Driving 🚗"

class Plane(Vehicle):
    def move(self):
        return "Flying ✈️"

class Boat(Vehicle):
    def move(self):
        return "Sailing ⛵"

# Example Usage
if __name__ == "__main__":
    vehicles = [Car(), Plane(), Boat()]

    for vehicle in vehicles:
        print(vehicle.move())

# Output:
# Driving 🚗
# Flying ✈️
# Sailing ⛵
    
