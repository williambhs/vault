Note** solved but tles on secret question groups, maybe revisit sometime because I don't understand the correct answer

----
Solution 1 (TLEs on some test cases)
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

int ops{0};

int n;

if (!(cin >> n))

{

return 1;

}

  

while (n > 0)

{

if (n >= 500)

{

n -= 500;

ops++;

continue;

}

  

else if (n >= 200)

{

n -= 200;

ops++;

continue;

}

  

else if (n >= 100)

{

n -= 100;

ops++;

int diff = abs(n - 100);

if (diff < 50)

{

ops++;

break;

}

else

{

break;

}

}

}

cout << ops;

  

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
Solution 2