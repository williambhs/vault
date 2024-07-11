

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

  

bool contains(vector<char> v, char c)

{

for (char ch : v)

{

if (ch == c)

return true;

}

return false;

}

  

int solve()

{

int n, m;

if (!(cin >> n >> m))

{

return 1;

}

  

vector<vector<char>> spotty(n, vector<char>(m));

vector<vector<char>> plain(n, vector<char>(m));

for (size_t i = 0; i < n; i++)

{

for (size_t j = 0; j < m; j++)

{

cin >> spotty[i][j];

}

}

for (size_t i = 0; i < n; i++)

{

for (size_t j = 0; j < m; j++)

{

cin >> plain[i][j];

}

}

  

int ans{0};

for (int i = 0; i < m; i++)

{

vector<char> currSpotty;

vector<char> currPlain;

for (size_t j = 0; j < n; j++)

{

currSpotty.pb(spotty[j][i]);

}

for (size_t k = 0; k < n; k++)

{

currPlain.pb(plain[k][i]);

}

bool noDupes = true;

  

for (size_t l = 0; l < sz(currPlain); l++)

{

if (contains(currSpotty, currPlain[l]))

noDupes = false;

}

if (noDupes)

{

ans++;

}

}

cout << ans;

  

return 0;

}

  

int32_t main()

{

freopen("cownomics.in", "r", stdin);

freopen("cownomics.out", "w", stdout);

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