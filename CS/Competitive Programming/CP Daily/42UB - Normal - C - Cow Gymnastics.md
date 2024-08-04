

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

int ans{0};

int k, n;

cin >> k >> n;

  

vector<vector<int>> matrix(k, vector<int>(n));

vector<vector<int>> vect(n, vector<int>(n));

for (size_t row = 0; row < k; row++)

{

for (size_t col = 0; col < n; col++)

{

int curr;

cin >> curr;

matrix[row][col] = --curr;

}

}

  

for (int cases = 0; cases < k; cases++)

{

for (int i = 0; i < n - 1; i++)

{

int curr = matrix[cases][i];

for (int j = i + 1; j < n; j++)

{

int next = matrix[cases][j];

vect[curr][next]++;

db(curr);

db(next);

db(vect);

}

}

}

  

for (auto i : vect)

{

for (auto j : i)

{

if (j == k)

ans++;

}

}

  

cout << ans;

return 0;

}

  

int32_t main()

{

freopen("gymnastics.in", "r", stdin);

freopen("gymnastics.out", "w", stdout);

#ifdef ONPC

freopen("ErrorStream.txt", "w", stderr);

#endif

ios::sync_with_stdio(0);

cin.tie(0);

solve();

#ifdef ONPC

cout << "__________________________" << endl;

cerr << endl

<< "finished in " << clock() * 1.0 / CLOCKS_PER_SEC << " sec" << endl;

#endif

}
```