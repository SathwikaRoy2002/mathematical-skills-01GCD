#include<bits/stdc++.h>
using namespace std;

int gCd(map<int, int> &mp, int mx) {
  int i, j;
  for (i = mx; i; i--) {
    int count = 0;
    for (j = i; j <= mx; j += i) {
      count += mp[j];
      if (count > 1) {
        return i;
      }
    }
  }
  return -1;
}

void solve()
{
    int n, a, i, mx = 0;
    cin >> n;
    map<int, int> mp;
    for (i = 0; i < n; i++) {
        cin >> a;
        mp[a]++;
        mx = max(mx, a);
    }
    cout << gCd(mp, mx) << '\n';
}
 
signed main()
{
    ios_base::sync_with_stdio(0);
    cin.tie(0);cout.tie(0);
    solve();
}
