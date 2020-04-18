//https://vjudge.net/problem/LightOJ-1224

#include <iostream>
#include <algorithm>

using namespace std;

#define MAX 4
#define print(x, ans) cout << "Case " << x << ": " << ans << endl

int index(char ch) {
    switch(ch) {
        case 'A': return ch - 65;
        case 'C': return ch - 66;
        case 'G': return ch - 69;
    }
    return 3;
}

struct Node {
    Node *child[MAX];
    int prefix;
};

Node *newNode() {
    Node *node = new Node();
    node->prefix = 0;
    for (int i = 0; i < MAX; ++i) {
        node->child[i] = NULL;
    }
    return node;
}

void insert(Node *root, string s, int &ans) {
    Node *p = root;
    for (int i = 0; i < s.size(); ++i) {
        int ch = index(s[i]);
        int depth = i + 1;
        if (p->child[ch] == NULL) {
            p->child[ch] = newNode();
        }
        p = p->child[ch];
        p->prefix++;
        ans = max(ans, p->prefix * depth);
    }
}

int main() {
    ios::sync_with_stdio(false);
    cin.tie(NULL);
    int t;
    cin >> t;
    for (int c = 1; c <= t; ++c) {
        Node *root = newNode();
        int n;
        cin >> n;
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            string s;
            cin >> s;
            insert(root, s, ans);
        }
        print(c, ans);
    }
}
