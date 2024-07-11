

----
```
#ifdef ONPC

#define _GLIBCXX_DEBUG

#define db(x) \

cerr << #x << " "; \

_print(x); \

cerr << endl;

#else

#define db(x)

#endif

#include <bits/stdc++.h>

#define sz(a) ((int)((a).size()))

#define all(x) (x).begin(), (x).end()

#define pb push_back

#define ppb pop_back

using namespace std;

// mt19937 rnd(239);

mt19937 rnd(chrono::steady_clock::now().time_since_epoch().count());

  

typedef long long ll;

typedef long double ld;

  

void _print(ll t) { cerr << t; }

void _print(int t) { cerr << t; }

void _print(string t) { cerr << t; }

void _print(char t) { cerr << t; }

void _print(double t) { cerr << t; }

void _print(unsigned long long t) { cerr << t; }

  

template <class T, class V>

void _print(pair<T, V> p);

template <class T>

void _print(vector<T> v);

template <class T>

void _print(set<T> v);

template <class T, class V>

void _print(map<T, V> v);

template <class T>

void _print(multiset<T> v);

  

template <class T, class V>

void _print(pair<T, V> p) { cerr << "{ " << p.first << ", " << p.second << " }"; }

template <class T>

void _print(vector<T> v)

{

cerr << "[ ";

for (T i : v)

{

_print(i);

cerr << " ";

}

cerr << "]";

}

template <class T>

void _print(set<T> v)

{

cerr << "[ ";

for (T i : v)

{

_print(i);

cerr << " ";

}

cerr << "]";

}

template <class T>

void _print(multiset<T> v)

{

cerr << "[ ";

for (T i : v)

{

_print(i);

cerr << " ";

}

cerr << "]";

}

template <class T, class V>

void _print(map<T, V> v)

{

cerr << "[ ";

for (auto i : v)

{

_print(i);

cerr << " ";

}

cerr << "]";

}

  

int solve()

{

int n;

if (!(cin >> n))

{

return 1;

}

  

map<char, int> mp;

for (size_t i = 0; i < n; i++)

{

// add all unique letters

string s1, s2;

if (!(cin >> s1 >> s2))

{

return 1;

}

map<char, int> s1freqMap;

for (size_t i = 0; i < s1.length(); i++)

{

s1freqMap[s1[i]]++;

}

  

for (size_t i = 0; i < s1.length(); i++)

{

mp[s1[i]]++;

}

for (size_t i = 0; i < s2.length(); i++)

{

char curr = s2[i];

s1freqMap[curr]--;

if (s1freqMap[curr] < 0)

mp[curr]++;

}

}

db(mp);

  

vector<int> arr(26, 0);

for (auto itr = mp.begin(); itr != mp.end(); itr++)

{

int pos = itr->first - 97;

arr[pos] += itr->second;

}

  

for (int num : arr)

{

cout << num << endl;

}

  

return 0;

}

  

int32_t main()

{

freopen("blocks.in", "r", stdin);

freopen("blocks.out", "w", stdout);

#ifdef ONPC

freopen("ErrorStream.txt", "w", stderr);

#endif

ios::sync_with_stdio(0);

cin.tie(0);

int TET = 1e9;

// cin >> TET;

for (int i = 1; i <= TET; i++)

{

if (solve())

{

break;

}

#ifdef ONPC

cout << "__________________________" << endl;

#endif

}

#ifdef ONPC

cerr << endl

<< "finished in " << clock() * 1.0 / CLOCKS_PER_SEC << " sec" << endl;

#endif

}
```