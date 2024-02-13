# Object Oriented Programming

Tags: In progress

# OOP With C++

### Create Your First Class

### Car Example

- g++ -o myprogram main.cpp car.cpp
- Code
    - car.h
        
        ```cpp
        #pragma once
        #include <iostream>
        #include <string>
        using namespace std;
        
        class Car
        {
        private:
            string maker;
            int model;
            string color;
        
        public:
            void set_maker(string m);
            string get_maker();
            void set_model(int m);
            int get_model();
        };
        ```
        
    - car.cpp
        
        ```cpp
        #include "car.h"
        
        void Car::set_maker(string m)
        {
            maker = m;
        
        }
        
        string Car::get_maker()
        {
            return maker;
        }
        
        void Car::set_model(int m)
        {
            model = m;
        }
        
        int Car::get_model()
        {
            return model;
        }
        ```
        
    - main.cpp
        
        ```cpp
        // main.cpp
        #include "car.h"
        #include <iostream>
        #include <string>
        
        using namespace std;
        
        int main()
        {
            Car c1;
        
            c1.set_maker("Honda");
            c1.set_model(2024);
        
            cout << "This Car made by " << c1.get_maker() << "\n";
            cout << "This Car model is " << c1.get_model() << "\n";
        
            return 0;
        }
        ```
        

### **Constructor & Destructor**

### **Constructor**

- "When you instantiate an object from a class in C++, the constructor is automatically called.”
- Code
    - car.h
        
        ```cpp
        #pragma once
        #include <iostream>
        #include <string>
        using namespace std;
        
        class Car
        {
        private:
            string maker;
            int model;
            string color;
        
        public:
            void set_maker(string m);
            string get_maker();
            void set_model(int m);
            int get_model();
        
            Car(/* args */);
          //  ~Car();
        };
        ```
        
    - car.cpp
        
        ```cpp
        #include "car.h"
        
        void Car::set_maker(string m)
        {
            maker = m;
        
        }
        
        string Car::get_maker()
        {
            return maker;
        }
        
        void Car::set_model(int m)
        {
            model = m;
        }
        
        int Car::get_model()
        {
            return model;
        }
        
        Car::Car(/* args */)
        {
            maker = "Honda";
            model = 2023;
            color = "white";
        }
        
        // Car::~Car()
        // {
        // }
        ```
        
    - main.cpp
        
        ```cpp
        // main.cpp
        #include "car.h"
        #include <iostream>
        #include <string>
        
        using namespace std;
        
        int main()
        {
            Car c1;
        
            cout << "This Car made by " << c1.get_maker() << "\n";
            cout << "This Car model is " << c1.get_model() << "\n";
        
            return 0;
        }
        ```
        

### **Constructor** Initialization **List Hard Code**

- Initializing member variables directly within the constructor’s declaration can improve performance.
- Code
    - car.h
        
        ```cpp
        #pragma once
        #include <iostream>
        #include <string>
        using namespace std;
        
        class Car
        {
        private:
            string maker;
            int model;
            string color;
        
        public:
            void set_maker(string m);
            string get_maker();
            void set_model(int m);
            int get_model();
        
            Car(/* args */);
          //  ~Car();
        };
        ```
        
    - car.cpp
        
        ```cpp
        #include "car.h"
        
        void Car::set_maker(string m)
        {
            maker = m;
        
        }
        
        string Car::get_maker()
        {
            return maker;
        }
        
        void Car::set_model(int m)
        {
            model = m;
        }
        
        int Car::get_model()
        {
            return model;
        }
        
        Car::Car() :maker("Honda"), model(2021), color("White")
        {
        
        }
        
        // Car::~Car()
        // {
        // }
        ```
        
    - main.cpp
        
        ```cpp
        // main.cpp
        #include "car.h"
        #include <iostream>
        #include <string>
        
        using namespace std;
        
        int main()
        {
            Car c1;
        
            cout << "This Car made by " << c1.get_maker() << "\n";
            cout << "This Car model is " << c1.get_model() << "\n";
        
            return 0;
        }
        ```
        
    - Here, we have hardcoded the initialization of the member variables inside the constructor. However, we want the user to initialize them.

### **Constructor** Initialization **List Value**

- Initializing member variables directly within the constructor’s declaration can improve performance.
- Code
    - car.h
        
        ```cpp
        #pragma once
        #include <iostream>
        #include <string>
        using namespace std;
        
        class Car
        {
        private:
            string maker;
            int model;
            string color;
        
        public:
            void set_maker(string m);
            string get_maker();
            void set_model(int m);
            int get_model();
        
            Car(string m , int mo , string c);
          //  ~Car();
        };
        ```
        
    - car.cpp
        
        ```cpp
        #include "car.h"
        
        void Car::set_maker(string m)
        {
            maker = m;
        
        }
        
        string Car::get_maker()
        {
            return maker;
        }
        
        void Car::set_model(int m)
        {
            model = m;
        }
        
        int Car::get_model()
        {
            return model;
        }
        
        Car::Car(string m , int mo , string c) :maker(m), model(mo), color(c)
        {
        
        }
        
        // Car::~Car()
        // {
        // }
        ```


        
    - main.cpp
        
        ```cpp
        // main.cpp
        #include "car.h"
        #include <iostream>
        #include <string>
        
        using namespace std;
        
        int main()
        {
            Car c1("Toyota",2022,"black");
            Car c2("FIAT",1985,"White");
        
            cout << "This Car made by " << c1.get_maker() << "\n";
            cout << "This Car model is " << c1.get_model() << "\n";
            cout << "This Car made by " << c2.get_maker() << "\n";
            cout << "This Car model is " << c2.get_model() << "\n";
        
            return 0;
        }
        ```
        
    - Here, we want the user to initialize the member variables.

### **Destructor**

- The destructor is called automatically when the object is destroyed.
- Since we are dynamically allocating memory for the object, we can release it in the destructor.
- Code
    - car.h
        
        ```cpp
        #pragma once
        #include <iostream>
        #include <string>
        using namespace std;
        
        class Car
        {
        private:
            string maker;
            int model;
            string color;
        
        public:
            void set_maker(string m);
            string get_maker();
            void set_model(int m);
            int get_model();
        
            Car(string m , int mo , string c);
            ~Car();
        };
        ```
        
    - car.cpp
        
        ```cpp
        #include "car.h"
        
        void Car::set_maker(string m)
        {
            maker = m;
        
        }
        
        string Car::get_maker()
        {
            return maker;
        }
        
        void Car::set_model(int m)
        {
            model = m;
        }
        
        int Car::get_model()
        {
            return model;
        }
        
        Car::Car(string m , int mo , string c) :maker(m), model(mo), color(c)
        {
        
        }
        
        Car::~Car()
        {
            cout << "Good Bye" << "\n";
        }
        ```
        
    - main.cpp
        
        ```cpp
        // main.cpp
        #include "car.h"
        #include <iostream>
        #include <string>
        
        using namespace std;
        
        int main()
        {
            Car c1("Toyota",2022,"black");
            Car c2("FIAT",1985,"White");
        
            cout << "This Car made by " << c1.get_maker() << "\n";
            cout << "This Car model is " << c1.get_model() << "\n";
            cout << "This Car made by " << c2.get_maker() << "\n";
            cout << "This Car model is " << c2.get_model() << "\n";
        
            return 0;
        }
        ```
        

### **Method and Constructor Overloading**

### Overload Method

- Method overloading allows multiple methods in a class with the same name.
- g++ -o my_program main.cpp calc.cpp
- Code
    - calc.cpp
        
        ```cpp
        #include "calc.h"
        
        int Calc::add(int num1, int num2)
        {
            return num1 + num2;
        }
        int Calc::add(int num1 ,int num2 ,int num3)
        {
            return num1 + num2 + num3;
        }
        float Calc::add(float num1 ,float num2)
        {
            return num1 + num2;
        }
        string Calc::add(string a, string b)
        {
            return a + b;
        }
        ```
        
    - main.cpp
        
        ```cpp
        #include "calc.h"
        #include <iostream>
        #include <string>
        
        int main()
        {
            Calc c1;
            cout << "This is version one " << c1.add(3,7) << "\n";
            cout << "This is version Tow " << c1.add(3,7,10) << "\n";
            cout << "This is version Three " << c1.add("Hello", " World") << "\n";
        }
        ```
        
    - calc.h
        
        ```cpp
        #pragma once
        #include <iostream>
        #include <string>
        using namespace std;
        class Calc
        {
        private:
        
        public:
            int add(int num1, int num2);
            int add(int num1 ,int num2 ,int num3);
            float add(float num1 ,float num2);
            string add(string a, string b);
            // Calc(/* args */);
            // ~Calc();
        };
        
        // Calc::Calc(/* args */)
        // {
        // }
        
        // Calc::~Calc()
        // {
        // }
        ```
        

### Resources

[https://www.youtube.com/playlist?list=PL1DUmTEdeA6KLEvIO0NyrkT91BVle8BOU](https://www.youtube.com/playlist?list=PL1DUmTEdeA6KLEvIO0NyrkT91BVle8BOU)
