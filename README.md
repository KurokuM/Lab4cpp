# Lab4cpp
Laborator 4 C++ DJ2202 Simboteanu Alexandru
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
EX1
#include <iostream>
#include <vector>
#include <numeric>

int main() {
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    
    int sum = std::accumulate(numbers.begin(), numbers.end(), 0 );
    
    std::cout << "Suma elementelor: " << sum << std::endl;

    return 0;
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
EX2
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> sortedVector = {1, 2, 3, 4, 5};

    bool found = std::binary_search(sortedVector.begin(), sortedVector.end(), 6);

    if (found) {
        std::cout << "Nahod" << std::endl;
    } else {
        std::cout << "Nenahod" << std::endl;
    }

    return 0;
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
EX3
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> numbers = {5,5,7,7,6,6,2,2,3,3,4};

    std::sort(numbers.begin(), numbers.end());
    auto last = std::unique(numbers.begin(), numbers.end());
    numbers.erase(last, numbers.end());

    for (int num : numbers) {
        std::cout << num << " ";
    }

    return 0;
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
EX4
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> vec1 = {1, 3, 5};
    std::vector<int> vec2 = {2, 4, 6};
    std::vector<int> result;

    std::merge(vec1.begin(), vec1.end(), vec2.begin(), vec2.end(), std::back_inserter(result));

    for (int num : result) {
        std::cout << num << " ";
    }

    return 0;
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
EX5
#include <iostream>
#include <algorithm>

int main() {
    std::string str = "radar";

    bool isPalindrome = std::equal(str.begin(), str.begin() + str.size()/2, str.rbegin());

    if (isPalindrome) {
        std::cout << "Este palindrom." << std::endl;
    } else {
        std::cout << "Nu este palindrom." << std::endl;
    }

    return 0;
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
EX6
#include <iostream>
#include <thread>

void printHello() {
    std::cout << "Hello ";
}

void printWorld() {
    std::cout << "World" << std::endl;
}

int main() {
    std::thread t1(printHello);
    std::thread t2(printWorld);

    t1.join();
    t2.join();

    return 0;
}
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////































