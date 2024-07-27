[striver](https://www.youtube.com/watch?v=RRVYpIET_RU)
[lower bound and upper bound](https://www.youtube.com/watch?v=edJ19qIL8WQ)
# C++ STL Library:
- STL stands for standard template library which contains a lot of pre-defined templates in terms of containers and classes which makes it very easy for developers or programmers to implement different data structures easily without having to write complete code and worry about space-time complexities. 

## STL is divided into four parts:
- Algorithms
- Containers
- Functions
- Iterators

### Containers
- Pairs : It's part of utility library.
	```cpp
	void explainPairs(){
		pair<int, int> p = {1, 2};
		cout << p.first << " " << p.second << endl;
		pair<int pair<int, int>> nested_p = { 1, {2, 3}};
		cout << p.first << " " << p.second.first << " " << p.second.second << endl;
		pair<int, int> arr[] = {{1, 2}, {3, 4}};
		cout << arr[1].first;
	}
	```

- Vectors : Vector is a container which is dynamic in nature means you can increase the size of it whenever you wish to. When you don't know the size of a particular DS use vector.
	```cpp
	// single ll ds maintain
	void explainVector() {
		vector<int> v; // -> {}
		vector.push_back(1); // {} -> {1};
		vector.emplace_back(2); // {1} -> {1, 2};

		vector<pair<int, int>> p;
		vector.push_back({1 , 2}); // {} -> {{1,2}};
		vector.emplace_back(3, 4); // {{1,2}} -> {{1,2}, {3,4}};

		vector<int> v(5,100); // {100, 100, 100, 100, 100}
		vector<int> v1(5); // {0, 0, 0, 0, 0}
		vector<int> v2(v1); // copy of v1

		cout << v[0] << v.at(0);
		// v.begin() -> It is **address** to the first vector element.
		vector<int>::iterator it = v.begin();
		it++;
		cout << *(it) << endl;
		vector<int>::iterator it = v.end(); // It is **next address** to the last element.
		vector<int>::iterator it = v.rbegin(); // rarely used vector<int>::iterator it = v.rend(); // rarely used cout << v.back();

		for(vector<int>::iterator it = v.begin(); it != v.end(); it++){
			cout << *(it) << endl;
		}
		for(auto it = v.begin(); it != v.end(); it++){
			cout << *(it) << endl;
		}

		for(auto it: v){
			cout << it << endl;
		}

		v.erase(v.begin() + 1);
		v.erase(v.begin() + 1, v.begin() + 4);

		vector<int> v(2,100); // {100, 100}
		v.insert(v.begin(), 300); // {300, 100, 100}
		v.insert(v.begin() + 1, 2, 10); // {300, 10, 10, 100, 100}
		vector<int> copy(2,50); // {50, 50}
		v.insert(v.begin(), copy.begin(), copy.end()); // {50, 50, 300, 10, 10, 100, 100}

		// {10, 20}
		v.size(); // 2
		v.popback(); // 10


		// v1 -> {10,20}
		// v2 -> {30,40}
		v1.swap(v2); // v1 -> {30,40}  v2 -> {10,20}


		v.clear(); // erases the entire vector

		cout << v.empty();
	}
	```


- LIST : 
	```cpp
	// doulbly ll DS maintain
	void explainList(){
		list<int> l; // {}
		l.push_back(2); // {2}
		l.emplace_back(4); // {2,4}

		// these two are extra in list than vector
		l.push_front(5); // {5,2,4}
		l.emplace_front(3); // {3,5,2,4}
	// rest function same as vector
	// begin, end, rbegin, rend, insert, clear, size, swap and empty
	}
	```

- Deque: 
	```cpp
	// doulbly ll DS maintain
	void explainDeque(){
		deque<int> d; // {}
		d.push_back(2); // {2}
		d.emplace_back(4); // {2,4}
		d.push_front(5); // {5,2,4}
		d.emplace_front(3); // {3,5,2,4}

		d.pop_back(); // {3,5,2}
		d.pop_front(); // {5,2}

		d.back();
		d.front();
	// rest function same as vector
	// begin, end, rbegin, rend, insert, clear, size, swap and empty
	}
	```

- Stack
	```cpp
	// doulbly ll DS maintain
	void explainStack(){
		stack<int> st; // {}
		st.push(1)// {1}
		st.push(2)// {2,1}
		st.push(3)// {3,2,1}
		st.emplace(4)// {4,3,2,1}

		// NOTE: st[2] is invalid
		cout << st.top(); // 4 
		st.pop(); // {3,2,1}
		st.size();
		st.empty();

		stack<int> st1,st2;
		st1.swap(st2);
	}
	```

- Queue:
	```cpp
	void explainQueue(){
		queue<int> q;
		q.push(1); // {1}
		q.push(2); // {1, 2}
		q.emplace(3); // {1, 2, 3}
		cout << q.back(); // 3
		cout << q.front(); // 1
		q.pop(); // 1
		q.size();
		q.empty();
	}
	```

- Priority Queue
	```cpp
	// push and pop ->O(log n); top -> O(1)
	void explainPQ(){
		// Maximum Heap
		priority_queue<int> pq;
		pq.push(1); // {1}
		pq.push(3); // {3,1}
		pq.emplace(2); // {3,2,1}
		cout << pq.top(); // 3
		q.pop(); // 3
		q.size();
		q.empty();

		// Minimum Heap
		priority_queue<int, vector<int>, greater<int>> pq;
		pq.push(5); // {5}
		pq.push(2); // {2, 5};
		pq.push(8); // {2, 5, 8};
		pq.push(10); // {2, 5, 8, 10};
		pq.top(); // 2
	}
	```

- SET:
	```cpp
	// sorted and unique
	// multiset -> sorted but can have duplicates
	// multiset<int> mst;
	// Unorder set -> unique but not sorted
	// unordered_set<int> ust; // lower_bound and upper_bound functions do not work.
	void explainSet(){
		set<int> st;
		st.insert(1); // {1};
		st.emplace(2); // {1,2};
		st.insert(2); // {1,2};
		st.insert(4); // {1,2,4};
		st.insert(3); // {1,2,3,4};

		auto it = set.find(3); // send address to the element.
		// itrator points to address.
		auto it = set.find(6); // not avaiable send set.end();

		st.erase(it);
		st.lower_bound();
		st.upper_bound();
	}
	```

- MAP:
	```cpp
	// in map, key are unique and sorted.
	// multimap everything same expect key can be duplicate. and mp[key] cannot be used here.
	// unorderedMap has unique key but not sorted.
	void explainMap(){
		map<int, int> mp; // {key,value}
		map<int, pair<int, int>> mpp;
		map<pair<int,int>, int> mkp;

		mp[1] = 2; {{1,2}};
		mp.emplace({3,1}); {{1,2}, {3,1}}
		mp.insert({2,4}); {{1,2},{2,4},{3,1}}

		mkp[{3,1}] = 2; {{{3,1},2}}
	}
	```


## Alogrithms
- sorting 
	```cpp
	sort(begin_iterator, end_iterator); // [begin_iterator, end_iterator)
	int a[5] = {1,4,3,5,2};
	sort(a, a+n); // increasing order
	sort(a, a+n, greater<int>); // decreasing order
	sort(v.begin(), v.end());
	```

- counting set(1) bits 
	```cpp
	int num = 7; // 00000111
	int count = _builtin_popcount(); // 3

	long long num = 123241342322;
	int cnt = _builtin_popcountll();
	```

- max and min element
	```cpp
	int a[5] = {1,4,3,5,2};
	int max = *max_element(a,a+n); // return address and we get value by *.
	int min = *min_element(a,a+n); // return address and we get value by *.
	
	```