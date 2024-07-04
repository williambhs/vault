

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

vector<pair<int, int>> arr;

for (size_t i = 0; i < 3; i++)

{

int c, m;

if (!(cin >> c >> m))

{

return 1;

}

pair<int, int> p = {c, m};

arr.pb(p);

}

  

int ops = 100;

db(arr);

int c1 = arr[0].first;

int m1 = arr[0].second;

int c2 = arr[1].first;

int m2 = arr[1].second;

int c3 = arr[2].first;

int m3 = arr[2].second;

  

while (ops != 0)

{

// pour 1 -> 2

if (m1 + m2 <= c2)

{

m2 += m1;

m1 = 0;

ops--;

if (ops == 0)

break;

}

  

else

{

m2 += m1;

m1 = m2 - c2;

m2 = c2;

ops--;

if (ops == 0)

break;

}

  

// pour 2 -> 3

if (m2 + m3 <= c3)

{

m3 += m2;

m2 = 0;

ops--;

if (ops == 0)

break;

}

  

else

{

m3 += m2;

m2 = m3 - c3;

m3 = c3;

ops--;

if (ops == 0)

break;

}

  

// pour 3 -> 1

if (m3 + m1 <= c1)

{

m1 += m3;

m3 = 0;

ops--;

if (ops == 0)

break;

}

  

else

{

m1 += m3;

m3 = m1 - c1;

m1 = c1;

ops--;

if (ops == 0)

break;

}

}

cout << m1 << endl

<< m2 << endl

<< m3 << endl;

  

return 0;

}

  

int32_t main()

{

freopen("mixmilk.in", "r", stdin);

freopen("mixmilk.out", "w", stdout);

#ifdef ONPC

freopen("ErrorStream.txt", "w", stderr);

#endif

ios::sync_with_stdio(0);

cin.tie(0);

int TET = 1e9;

// cin >> TET;

for (int i = 1; i <= 1; i++)

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