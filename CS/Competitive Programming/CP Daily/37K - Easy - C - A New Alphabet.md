

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

map<char, string> mp;

mp['a'] = "@";

mp['b'] = "8";

mp['c'] = "(";

mp['d'] = "|)";

mp['e'] = "3";

mp['f'] = "#";

mp['g'] = "6";

mp['h'] = "[-]";

mp['i'] = "|";

mp['j'] = "_|";

mp['k'] = "|<";

mp['l'] = "1";

mp['m'] = "[]\\/[]";

mp['n'] = "[]\\[]";

mp['o'] = "0";

mp['p'] = "|D";

mp['q'] = "(,)";

mp['r'] = "|Z";

mp['s'] = "$";

mp['t'] = "']['";

mp['u'] = "|_|";

mp['v'] = "\\/";

mp['w'] = "\\/\\/";

mp['x'] = "}{";

mp['y'] = "`/";

mp['z'] = "2";

string n;

if (!getline(cin, n))

{

return 1;

}

string str;

for (char c : n)

{

if (isalpha(c))

c = tolower(c);

if (mp.find(c) == mp.end())

{

str += c;

}

else

{

str += mp[c];

}

}

cout << str;

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

