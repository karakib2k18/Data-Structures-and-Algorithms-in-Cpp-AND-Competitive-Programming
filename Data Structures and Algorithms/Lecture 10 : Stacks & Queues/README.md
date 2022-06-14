# ##Lecture 9 : Linked List 2

---



---

### Stack Introduction
![image](https://user-images.githubusercontent.com/57065763/173322585-6f4fd52c-2af0-4a42-bcee-b529ca36cd7f.png)
### Stack in Recursion
![image](https://user-images.githubusercontent.com/57065763/173323082-847c804d-46f9-4299-b336-6ab09b2a289f.png)
### Stack Using Array
![image](https://user-images.githubusercontent.com/57065763/173324457-4298275b-3ef9-4d2c-bf1e-e08154c2e707.png)
![image](https://user-images.githubusercontent.com/57065763/173328643-9fb5a6f8-6f13-4cfb-b4a8-d7ae8f9aa17b.png)
![image](https://user-images.githubusercontent.com/57065763/173329979-56cc1d1c-b6ba-42ee-ad5b-99ba80f44bfa.png)
![image](https://user-images.githubusercontent.com/57065763/173342472-078ef80f-ad2c-486f-a454-4f7cff46cfcc.png)


```cpp
// insert element in static array
void push(int element) {
    if(nextIndex == capacity) {
        cout << "Stack full " << endl;
        return;
    }
    data[nextIndex] = element;
    nextIndex++;
}
```

```cpp
// return the number of elements present in my stack
int size() {
    return nextIndex;
}
```

```cpp
bool isEmpty() {
    /*
    if(nextIndex == 0) {
        return true;
    }
    else {
        return false;
    }
    */
    return nextIndex == 0; // index 0 hole empty and true return korbe. And empty e hobe.
}
```

```cpp
// delete element
int pop() {
    if(isEmpty()) {
        cout << "Stack is empty " << endl;
        return INT_MIN;	
    }
    nextIndex--;
    return data[nextIndex];
}

int top() {
    if(isEmpty()) {
        cout << "Stack is empty " << endl;
        return INT_MIN;	
    }
    return data[nextIndex - 1];
}
```
```cpp
//find top element
int top() {
    if(isEmpty()) {
        cout << "Stack is empty " << endl;
        return INT_MIN;	
    }
    return data[nextIndex - 1];
}
```

```cpp
#include <iostream>
#include <climits>
using namespace std;

class StackUsingArray {
	int *data;
	int nextIndex;
	int capacity;	

	public :

	StackUsingArray(int totalSize) {
		data = new int[totalSize];
		nextIndex = 0;
		capacity = totalSize;
	}

	// return the number of elements present in my stack
	int size() {
		return nextIndex;
	}

	bool isEmpty() {
        /*
		if(nextIndex == 0) {
			return true;
		}
		else {
			return false;
		}
        */
		return nextIndex == 0;
	}

	// insert element
	void push(int element) {
		if(nextIndex == capacity) {
			cout << "Stack full " << endl;
			return;
		}
		data[nextIndex] = element;
		nextIndex++;
	}

	// delete element
	int pop() {
		if(isEmpty()) {
			cout << "Stack is empty " << endl;
			return INT_MIN;	
		}
		nextIndex--;
		return data[nextIndex];
	}

	int top() {
		if(isEmpty()) {
			cout << "Stack is empty " << endl;
			return INT_MIN;	
		}
		return data[nextIndex - 1];
	}
};


int main() {
	StackUsingArray s(4);
	s.push(10);
	s.push(20);
	s.push(30);
	s.push(40);
	s.push(50);

	cout << s.top() << endl;
	cout << s.pop() << endl;
	cout << s.pop() << endl;
	cout << s.pop() << endl;
	cout << s.size() << endl;
	cout << s.isEmpty() << endl;
}

```

### Dynamic Stack
![image](https://user-images.githubusercontent.com/57065763/173344003-a3992ce2-cc6e-45c7-a5e6-3c4488b11476.png)



```cpp
// creating dynamically stack
public :

StackUsingArray() {
    data = new int[4];
    nextIndex = 0;
    capacity = 4;
}

```

```cpp
// insert element and increment size dynamically
void push(int element) {
    if(nextIndex == capacity) {
        int *newData = new int[2 * capacity];
        for(int i = 0; i < capacity; i++) {
            newData[i] = data[i];
        }
        capacity *= 2;
        delete [] data;
        data = newData;
        /*cout << "Stack full " << endl;
        return;*/
    }
    data[nextIndex] = element;
    nextIndex++;
}
```

```cpp
#include <iostream>
#include <climits>
using namespace std;


class StackUsingArray {
	int *data;
	int nextIndex;
	int capacity;	

	public :

	StackUsingArray() {
		data = new int[4];
		nextIndex = 0;
		capacity = 4;
	}

	// return the number of elements present in my stack
	int size() {
		return nextIndex;
	}

	bool isEmpty() {
		/*
		if(nextIndex == 0) {
			return true;
		}
		else {
			return false;
		}
		*/

		return nextIndex == 0;
	}

	// insert element
	void push(int element) {
		if(nextIndex == capacity) {
			int *newData = new int[2 * capacity];
			for(int i = 0; i < capacity; i++) {
				newData[i] = data[i];
			}
			capacity *= 2;
			delete [] data;
			data = newData;
			/*cout << "Stack full " << endl;
			return;*/
		}
		data[nextIndex] = element;
		nextIndex++;
	}

	// delete element
	int pop() {
		if(isEmpty()) {
			cout << "Stack is empty " << endl;
			return INT_MIN;	
		}
		nextIndex--;
		return data[nextIndex];
	}
	int top() {
		if(isEmpty()) {
			cout << "Stack is empty " << endl;
			return INT_MIN;	
		}
		return data[nextIndex - 1];
	}

};


int main() {
	StackUsingArray s;
	s.push(10);
	s.push(20);
	s.push(30);
	s.push(40);
	s.push(50);

	cout << s.top() << endl;
	cout << s.pop() << endl;
	cout << s.pop() << endl;
	cout << s.pop() << endl;
	cout << s.size() << endl;
	cout << s.isEmpty() << endl;

}

```

# Some MCQ::
![image](https://user-images.githubusercontent.com/57065763/173502589-82b6d545-3ef1-4a73-a44a-17ca4ced45c3.png)
![image](https://user-images.githubusercontent.com/57065763/173502634-ab81644b-22f9-43de-a9b7-b501a4cd3ef4.png)
![image](https://user-images.githubusercontent.com/57065763/173502660-134c30ea-0783-4946-822c-e42e68ce6549.png)
![image](https://user-images.githubusercontent.com/57065763/173502682-915220f2-99c3-4e07-bda4-6b06c3ceda16.png)
![image](https://user-images.githubusercontent.com/57065763/173502717-279b2966-cdab-4373-8b1f-3dd063b93d1d.png)


### Templates

![image](https://user-images.githubusercontent.com/57065763/173515982-6c27daca-71a0-4b30-8430-ded8450d110f.png)
![image](https://user-images.githubusercontent.com/57065763/173524276-f7f915d1-17b5-45ee-a548-b42452f3a2ae.png)
![image](https://user-images.githubusercontent.com/57065763/173526170-ba8b2862-39d2-4f83-8b29-959c673bf2c8.png)
![image](https://user-images.githubusercontent.com/57065763/173526669-b0ba02ae-f632-43db-8087-e4acea223c80.png)
![image](https://user-images.githubusercontent.com/57065763/173526814-b7b95045-7da6-4b7f-ac55-9dd9968a45de.png)


### Stack Using Templates
==>> code here only
### Stack Using LL Introduction
![image](https://user-images.githubusercontent.com/57065763/173547154-002b1b5b-d732-43c6-b404-fe73057b89df.png)
![image](https://user-images.githubusercontent.com/57065763/173548250-33645248-459e-48fc-a0a1-06b3f5a018e1.png)
![image](https://user-images.githubusercontent.com/57065763/173549820-a13563bd-aa1f-4c60-971f-c44776ff856e.png)
![image](https://user-images.githubusercontent.com/57065763/173550554-a637670e-e9a2-4388-8ae0-aee2f31607ad.png)
![image](https://user-images.githubusercontent.com/57065763/173551083-387a55c9-071b-47ae-816e-1076d9752594.png)
![image](https://user-images.githubusercontent.com/57065763/173553864-161a5a80-7ccf-43de-9ff5-c84670267854.png)
![image](https://user-images.githubusercontent.com/57065763/173553164-dbcdb822-8ca2-4af6-a1e8-df317b5a39ea.png)
![image](https://user-images.githubusercontent.com/57065763/173553898-9015167f-dc52-4a2c-a058-5265ee155d25.png)


### Code: Midpoint of LL - QUESTION-1