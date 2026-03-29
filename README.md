# Ocado-and-Umali---M046
import 'dart:io';

void main() {
  List<Map<String, dynamic>> items = [];

  while (true) {
    print("\n1. Add");
    print("2. View");
    print("3. Update");
    print("4. Delete");
    print("5. Exit");
    stdout.write("Choice: ");

    String? choice = stdin.readLineSync();

    if (choice == '1') {
      stdout.write("Name: ");
      String? name = stdin.readLineSync();

      stdout.write("Qty: ");
      int qty = int.parse(stdin.readLineSync()!);

      items.add({"name": name ?? "", "qty": qty});
      print("Added");

    } else if (choice == '2') {
      for (int i = 0; i < items.length; i++) {
        print("${i + 1}. ${items[i]['name']} (${items[i]['qty']})");
      }

    } else if (choice == '3') {
      stdout.write("Number: ");
      int i = int.parse(stdin.readLineSync()!) - 1;

      stdout.write("New name: ");
      items[i]['name'] = stdin.readLineSync();

      stdout.write("New qty: ");
      items[i]['qty'] = int.parse(stdin.readLineSync()!);

      print("Updated");

    } else if (choice == '4') {
      stdout.write("Number: ");
      int i = int.parse(stdin.readLineSync()!) - 1;

      items.removeAt(i);
      print("Deleted");

    } else if (choice == '5') {
      break;

    } else {
      print("Invalid");
    }
  }
}
