# HackerRank-Problem-Solving-Basic
Hackerrank Problem solving quiz questions


## 1- String Anagram --> treick to use a map and sort the dictionary words

```
vector<int> stringAnagram(vector<string> dictionary, vector<string> query) {
//if empty return
	if (dictionary.empty() || query.empty())
		return std::vector<int>();

	std::map<string,int>setquery;
	
  //sorting and adding to the map
	for (auto &dic : dictionary) {
		std::sort(dic.begin(), dic.end());

		if (setquery.find(dic) != setquery.end()) {
			setquery[dic]++;
		}
		else {
			setquery.insert({ dic,1 });
		}
	}
	
  //sroting the queries
	for (auto& q : query) {
		std::sort(q.begin(), q.end());
	}

	//pushing back the results by matching the strings
	std::vector<int>res{};
	for (auto &q : query) {
		res.push_back(setquery.find(q) != setquery.end() ? setquery.at(q) : 0);
	}

	for (auto num : res) {
		std::cout << num << std::endl;
	}

	return res;
}


```
