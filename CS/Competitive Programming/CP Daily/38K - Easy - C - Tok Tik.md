

----
```
#ifdef ONPC

#define _GLIBCXX_DEBUG

#endif

#include <bits/stdc++.h>

#define sz(a) ((int)((a).size()))

using namespace std;

// mt19937 rnd(239);

mt19937 rnd(chrono::steady_clock::now().time_since_epoch().count());

typedef long long ll;

typedef long double ld;

int solve()

{

int n;

if (!(cin >> n))

{

return 1;

}

map<string, int> mp;

for (size_t i = 0; i < n; i++)

{

string name;

int views;

cin >> name >> views;

mp[name] += views;

}

auto itr = mp.begin();

string ans = itr->first;

int max = itr->second;

for (pair p : mp)

{

if (p.second > max)

{

max = p.second;

ans = p.first;

}

}

cout << ans;

return 0;

}

int32_t main()

{

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