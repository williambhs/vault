

----
```#ifdef ONPC

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

int n, m;

if (!(cin >> n >> m))

{

return 1;

}

if (m % n != 0)

{

int tot = m;

while (tot > 0)

{

for (int i = 0; i < m / n + 1; i++)

{

cout << "*";

}

cout << "\n";

tot -= ((m / n) + 1);

if (tot % (m / n) == 0)

{

while (tot != 0)

{

for (int j = 0; j < m / n; j++)

{

cout << "*";

}

cout << "\n";

tot -= m / n;

}

}

}

}

else

{

for (size_t i = 0; i < n; i++)

{

for (size_t j = 0; j < m / n; j++)

{

cout << "*";

}

cout << "\n";

}

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