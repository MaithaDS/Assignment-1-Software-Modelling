# Assignment-1-Software-Modelling
class User:
    """Class to represent a User of the airline system"""

    def __init__(self, username, password, booking_info):
        self.username = username
        self.password = password
        self.booking_info = booking_info

    def access_app_or_website(self):
        pass  # Method to allow the user to access the airline's mobile app or website

    def select_upgrade_option(self):
        pass  # Method to allow the user to select an upgrade option for their desired flight

    def confirm_upgrade(self):
        pass  # Method to confirm the selected upgrade option

    def make_payment(self):
        pass  # Method to handle the payment process if applicable


class AirlineSystem:
    """Class to represent an Airline System"""

    def __init__(self, available_upgrade_options, upgrade_prices, confirmation_email_template):
        self.available_upgrade_options = available_upgrade_options
        self.upgrade_prices = upgrade_prices
        self.confirmation_email_template = confirmation_email_template

    def display_upgrade_options(self):
        pass  # Method to display available upgrade options to the user

    def update_booking(self):
        pass  # Method to update the user's booking with the new seat assignment after confirmation

    def send_confirmation_email(self):
        pass  # Method to send a confirmation email or notification to the user after the upgrade process


class Seat:
    """Class to represent a Seat available for upgrade"""

    def __init__(self, seat_type, seat_number, price):
        self.seat_type = seat_type
        self.seat_number = seat_number
        self.price = price

    def get_seat_type(self):
        return self.seat_type  # Method to retrieve the type of the seat

    def get_price(self):
        return self.price  # Method to retrieve the price of upgrading to this seat


class Booking:
    """Class to represent a Booking made by the user"""

    def __init__(self, flight_details, seat_assignment):
        self.flight_details = flight_details
        self.seat_assignment = seat_assignment

    def get_flight_details(self):
        return self.flight_details  # Method to retrieve details about the booked flight

    def get_seat_assignment(self):
        return self.seat_assignment  # Method to retrieve the assigned seat

    def update_seat_assignment(self, new_seat_assignment):
        self.seat_assignment = new_seat_assignment  # Method to update the seat assignment after an upgrade is confirmed


# Example usage
if __name__ == "__main__":
    # Creating sample objects
    user = User("Maitha", "password123", {"flight": "1629", "seat": "Economy"})
    airline_system = AirlineSystem(["Business Class", "First Class"], {"Business Class": 100, "First Class": 200}, "Confirmation email template")
    seat = Seat("Business Class", "2A", 100)
    booking = Booking("Flight 1629", "Economy")

    # Accessing user's booking information
    print("User's Booking Information:")
    print("Flight:", user.booking_info["flight"])
    print("Seat:", user.booking_info["seat"])

    # Displaying available upgrade options
    print("\nAvailable Upgrade Options:")
    print(airline_system.available_upgrade_options)

    # Displaying seat information
    print("\nSeat Information:")
    print("Seat Type:", seat.get_seat_type())
    print("Seat Price:", seat.get_price())

    # Updating user's booking with new seat assignment
    new_seat_assignment = "First Class"
    booking.update_seat_assignment(new_seat_assignment)
    print("\nUpdated Booking Information:")
    print("Flight:", booking.get_flight_details())
    print("New Seat Assignment:", booking.get_seat_assignment())
