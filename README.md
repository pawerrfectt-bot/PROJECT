# PROJECT
GEOMETRIC SHAPE AREA CALCULATOR
import java.util.Scanner;

abstract class Shape {
    abstract double calculateArea();
}

class Circle extends Shape {
    double radius;
    Circle(double r) { radius = r; }
    double calculateArea() { return Math.PI * radius * radius; }
}

class Rectangle extends Shape {
    double length, width;
    Rectangle(double l, double w) { length = l; width = w; }
    double calculateArea() { return length * width; }
}

class Triangle extends Shape {
    double base, height;
    Triangle(double b, double h) { base = b; height = h; }
    double calculateArea() { return 0.5 * base * height; }
}

class Square extends Shape {
    double side;
    Square(double s) { side = s; }
    double calculateArea() { return side * side; }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int choice;

        do {
            System.out.println("1. Circle\n2. Rectangle\n3. Triangle\n4. Square\n5. Exit");
            System.out.print("Enter choice: ");
            choice = sc.nextInt();

            switch(choice) {
                case 1:
                    System.out.print("Enter radius: ");
                    double r = sc.nextDouble();
                    System.out.println("Area = " + new Circle(r).calculateArea());
                    break;
                case 2:
                    System.out.print("Enter length and width: ");
                    double l = sc.nextDouble();
                    double w = sc.nextDouble();
                    System.out.println("Area = " + new Rectangle(l,w).calculateArea());
                    break;
                case 3:
                    System.out.print("Enter base and height: ");
                    double b = sc.nextDouble();
                    double h = sc.nextDouble();
                    System.out.println("Area = " + new Triangle(b,h).calculateArea());
                    break;
                case 4:
                    System.out.print("Enter side: ");
                    double s = sc.nextDouble();
                    System.out.println("Area = " + new Square(s).calculateArea());
                    break;
            }
        } while(choice != 5);

        sc.close();
    }
}
