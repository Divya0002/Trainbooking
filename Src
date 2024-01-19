import java.util.HashMap;
import java.util.Scanner;

public class Cart8 {
	public HashMap<String, Integer> BookedTrains;

	public Cart8() {
		BookedTrains = new HashMap<>();
	}

	public static HashMap<String, String> trainsWithAvailablity = new HashMap<>();
	public static HashMap<String, String> trainsWithDetails = new HashMap<>();
	public static Scanner sc = new Scanner(System.in);
	static {

		trainsWithDetails.put("101", "Source : Katpadi Destination : Chennai Ticket Cost : R.S.500");
		trainsWithDetails.put("102", " Source : Katpadi Destination : Madurai Ticket Cost : R.S.100");
		trainsWithDetails.put("103", "Source : Katpadi Destination : Thirpathi Ticket Cost : R.S.400");
		trainsWithDetails.put("104", "Source : Katpadi Destination : thiruchi Ticket Cost : R.S. 100");
		trainsWithDetails.put("105", " Source : Katpadi Destination : walaja Ticket Cost : R.S.50");

		trainsWithAvailablity.put("101", "10");
		trainsWithAvailablity.put("102", "5");
		trainsWithAvailablity.put("103", "4");
		trainsWithAvailablity.put("104", "7");
		trainsWithAvailablity.put("105", "5");
	}

	public static void main(String[] args) {

		Cart8 tt = new Cart8();
		while (true) {
			menu();
			int n = getUserData("Please select an option[1-4] for further assistence:");
			switch (n) {
			case 1:
				availability(tt);
				break;
			case 3:
				tt.canceling(tt);
				break;
			case 2:
				tt.displaying(tt);
				break;
			default:
				System.out.println("Thank you for using the railway services");
				System.exit(0);
			}
		}
	}

	public static void menu() {
		System.out.println("Welcome to the Railway Reservation System.....");
		System.out.println("");
		System.out.println("1.Check Available Trains / Seat Availablity / Book ");
		System.out.println("2.Display Ticket Details.");
		System.out.println("3.Cancel a Ticket.");
		System.out.println("Any other number to exit");
	}

	public static void availability(Cart8 tt) {
		System.out.println("Available trains");
		displayData(trainsWithDetails, " ");
		String value = getUserData("[ Enter train code to display seats and enter any other number to go back to main menu ]").toString();
		if (trainsWithAvailablity.containsKey(value)) {
			if (Integer.parseInt(trainsWithAvailablity.get(value)) == 0) {
				System.out.println("No Tickets Available...\n");

			} else {
				System.out.println("Seats available :" + trainsWithAvailablity.get(value));
				Integer isBooking = getUserData("To Book train press 1 and any other number to go back to main menu");
				if (isBooking.equals(1)) {
					trainsWithAvailablity.put(value, Integer.toString(Integer.parseInt(trainsWithAvailablity.get(value)) - 1));
					tt.bookedTickets(value);
					System.out.println("your ticket is booked");
				}
			}
		}else {
			System.out.println("Train Details not found");
		}
	}

	private void bookedTickets(String trainNo) {
		if (BookedTrains.containsKey(trainNo)) {
			BookedTrains.put(trainNo, BookedTrains.get(trainNo) + 1);
		} else {
			BookedTrains.put(trainNo, 1);
		}
	}

	public static void displayData(HashMap<String, String> trainsData, String message) {
		int i = 1;
		for (String key : trainsData.keySet()) {
			System.out.println(i++ + ") " + key + message + trainsData.get(key));
		}
	}

	public static Integer getUserData(String message) {
		while (true) {
			try {
				System.out.println(message);
				int i = sc.nextInt();
				return i;
			} catch (Exception e) {
				System.out.println("Invalid data kindly enter correct data");
				sc.next();
			}
		}

	}

	private void canceling(Cart8 obj) {
		displaying(obj);
		String trainCode = getUserData("Enter train code to cancel or any other number to go back").toString();
		if (obj.BookedTrains.containsKey(trainCode)) {
			obj.BookedTrains.remove(trainCode);
			System.out.println("Ticket is canceled sucessfully");
			trainsWithAvailablity.put(trainCode, Integer.toString(Integer.parseInt(trainsWithAvailablity.get(trainCode)) + 1));
		}else {
			System.out.println("Train number not found");
		}
	}

	public void displaying(Cart8 obj) {
		if (obj.BookedTrains.isEmpty()) {
			System.out.println("No data Available");
			return;
		}
		System.out.println("------------------------------------------------------------------------------------------");
		System.out.println("Train No \t | Train Details \t 					|  tickets count ");
		for (String s : obj.BookedTrains.keySet()) {
			System.out.println(s + "\t | " + trainsWithDetails.get(s) + "\t | " + BookedTrains.get(s));
		}
		System.out.println("------------------------------------------------------------------------------------------");

	}
}
