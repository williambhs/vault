

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

vector<int> arr;

for (size_t i = 0; i < n; i++)

{

int num;

cin >> num;

arr.push_back(num);

}

for (int i = arr.size() - 1; i >= 0; i--)

{

cout << arr[i] << endl;

}

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