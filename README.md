#include <iostream>
using namespace std;

// Base class definition
class Base {
private:
    int secret;

protected:
    int protect;

public:
    int access;

    // Default constructor to initialize data members
    Base() : secret(1), protect(2), access(3) {}

    // Member functions to access private and protected members
    int getSecret() {
        return secret;
    }

    int getProtect() {
        return protect;
    }
};

// Derived class with private inheritance
class Derived_Private : private Base {
public:
    void show() {
        cout << "Derived_Private:" << endl;
        // Accessing private member using a public getter
        cout << "Secret (via getter): " << getSecret() << endl;
        cout << "Protect (via getter): " << getProtect() << endl;
        cout << "Access: " << access << endl;
    }
};

// Derived class with protected inheritance
class Derived_Protected : protected Base {
public:
    void show() {
        cout << "Derived_Protected:" << endl;
        // Accessing private member using a public getter
        cout << "Secret (via getter): " << getSecret() << endl;
        cout << "Protect (via getter): " << getProtect() << endl;
        cout << "Access: " << access << endl;
    }
};

// Derived class with public inheritance
class Derived_Public : public Base {
public:
    void show() {
        cout << "Derived_Public:" << endl;
        // Accessing private member using a public getter
        cout << "Secret (via getter): " << getSecret() << endl;
        cout << "Protect (via getter): " << getProtect() << endl;
        cout << "Access: " << access << endl;
    }
};

int main() {
    Derived_Private dPrivate;
    Derived_Protected dProtected;
    Derived_Public dPublic;

    dPrivate.show();
    cout << endl;

    dProtected.show();
    cout << endl;

    dPublic.show();
    cout << endl;

    return 0;
}
