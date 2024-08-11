# String
- Toggle the Case of a string.(Upper or lower case).
	```cpp
	// O(n)
	string str = "Hello"; // O/P -> hELLO
	
	for(int i = 0; i < str.size(); i++){
		if(str[i] >= 'A' && str[i] <= 'Z'){
			str[i] += 32;
		} else if(str[i] >= 'a' && str[i] <= 'z'){
			str[i] -= 32;
		}
	}
	```

- Counting consonants and vowels
	```cpp
	// O(n)
	string str = "Hello"; // O/P -> hELLO
	
	for(int i = 0; i < str.size(); i++){
		if(str[i] == 'A' || str[i] == 'E' || str[i] == 'I' || str[i] == 'O' || str[i] == 'U' || str[i] == 'a' || str[i] == 'e' || str[i] == 'i' || str[i] == 'o' || str[i] == 'u'){
			// vowel count increase;
		} else if (str[i] >= 'A' && str[i] <= 'Z' && str[i] >= 'a' && str[i] <= 'z') {
			// consonant count increase;
		}
	}
	```

- Counting words in string
	```cpp
	// O(n)
	string str = "Hello"; // O/P -> hELLO

	int word = 0;
	for(int i = 0; i < str.size(); i++){
		if(str[i] == ' ' && str[i + 1] != " "){
			word++;
		}
	}
	```

- Validating a string with alphabets and numbers only
	```cpp
	// O(n)
	string str = "Hello"; // O/P -> hELLO

	int word = 0;
	for(int i = 0; i < str.size(); i++){
		if(str[i] >= 'A' && str[i] <= 'Z' && str[i] >= 'a' && str[i] <= 'z' && str[i] >= '1'&& str[i] <= '9'){
			// valid string
		}
	}
	```


- Reversing a string
	- Using Extra array and fill using traversing in reverse order
	- Using two pointers : start, last and swap their location till start < last

- Comparing Two string
- Finding Duplicate in an string