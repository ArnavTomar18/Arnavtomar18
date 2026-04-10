# 💫 About Me:
💻 I'm currently working on:<br>Building AI-powered applications including a Sentiment Intelligence Engine with 18+ ML models and real-time recommendation systems.<br><br>🤝 I'm looking to collaborate on:<br>Open-source AI/ML projects, data-driven applications, and full-stack ML systems using FastAPI + React.<br><br>🛠️ I'm looking for help with:<br>Scaling ML models, improving deployment pipelines, and optimizing recommendation systems.<br><br>🌱 I'm currently learning:<br>Advanced Machine Learning, NLP, and system design for AI applications.<br><br>💬 Ask me about:<br>Machine Learning, Data Analysis, Sentiment Analysis, and building AI projects from scratch.<br><br>⚡ Fun fact:<br>I built a multi-domain AI platform before finishing my first year of engineering.


## 🌐 Socials:
[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white)](https://instagram.com/arnavtomar.18) [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/arnavtomar18) [![Reddit](https://img.shields.io/badge/Reddit-%23FF4500.svg?logo=Reddit&logoColor=white)](https://reddit.com/user/Beautiful_Garage6103) [![X](https://img.shields.io/badge/X-black.svg?logo=X&logoColor=white)](https://x.com/arnavtomar_18) [![email](https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white)](mailto:arnavtomar1812007@gmail.com) 

# 💻 Tech Stack:
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white) ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white) ![Anaconda](https://img.shields.io/badge/Anaconda-%2344A833.svg?style=for-the-badge&logo=anaconda&logoColor=white) ![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi) ![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB) ![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-4479A1.svg?style=for-the-badge&logo=mysql&logoColor=white) ![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white) ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=for-the-badge&logo=Canva&logoColor=white) ![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![Plotly](https://img.shields.io/badge/Plotly-%233F4F75.svg?style=for-the-badge&logo=plotly&logoColor=white) ![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white) ![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)
# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=arnavtomar18&theme=dracula&hide_border=false&include_all_commits=true&count_private=false)<br/>
![](https://nirzak-streak-stats.vercel.app/?user=arnavtomar18&theme=dracula&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=arnavtomar18&theme=dracula&hide_border=false&include_all_commits=true&count_private=false&layout=compact)

## 🏆 GitHub Trophies
![](https://github-profile-trophy.vercel.app/?username=arnavtomar18&theme=dracula&no-frame=false&no-bg=false&margin-w=4)

### 🔝 Top Contributed Repo
![](https://github-contributor-stats.vercel.app/api?username=arnavtomar18&limit=5&theme=dark&combine_all_yearly_contributions=true)

---
[![](https://visitcount.itsvg.in/api?id=arnavtomar18&icon=0&color=0)](https://visitcount.itsvg.in)

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->


You’ve got a full DAA lab chunk here. I’ll give you clean C++ code + sample output for each (Lab 9–15). No fluff.


---

✅ Lab 9: Longest Common Subsequence (LCS)

Code

#include <iostream>
#include <vector>
using namespace std;

int lcs(string X, string Y) {
    int m = X.length(), n = Y.length();
    vector<vector<int>> dp(m+1, vector<int>(n+1, 0));

    for(int i=1;i<=m;i++){
        for(int j=1;j<=n;j++){
            if(X[i-1]==Y[j-1])
                dp[i][j]=1+dp[i-1][j-1];
            else
                dp[i][j]=max(dp[i-1][j],dp[i][j-1]);
        }
    }
    return dp[m][n];
}

int main() {
    string X = "ABCBDAB", Y = "BDCAB";
    cout << "LCS Length: " << lcs(X,Y);
}

Output

LCS Length: 4


---

✅ Lab 10: N-Queens Problem

Code

#include <iostream>
using namespace std;

#define N 4

bool isSafe(int board[N][N], int row, int col) {
    for(int i=0;i<col;i++)
        if(board[row][i]) return false;

    for(int i=row,j=col;i>=0 && j>=0;i--,j--)
        if(board[i][j]) return false;

    for(int i=row,j=col;j>=0 && i<N;i++,j--)
        if(board[i][j]) return false;

    return true;
}

bool solve(int board[N][N], int col) {
    if(col>=N) return true;

    for(int i=0;i<N;i++){
        if(isSafe(board,i,col)){
            board[i][col]=1;
            if(solve(board,col+1)) return true;
            board[i][col]=0;
        }
    }
    return false;
}

int main(){
    int board[N][N]={0};

    if(solve(board,0)){
        for(int i=0;i<N;i++){
            for(int j=0;j<N;j++)
                cout<<board[i][j]<<" ";
            cout<<endl;
        }
    }
}

Output

0 0 1 0
1 0 0 0
0 0 0 1
0 1 0 0


---

✅ Lab 11: Travelling Salesman Problem (TSP - brute force)

Code

#include <iostream>
#include <climits>
using namespace std;

#define N 4

int tsp(int graph[N][N], bool visited[], int curr, int count, int cost, int &ans) {
    if(count == N && graph[curr][0]) {
        ans = min(ans, cost + graph[curr][0]);
        return ans;
    }

    for(int i=0;i<N;i++){
        if(!visited[i] && graph[curr][i]){
            visited[i]=true;
            tsp(graph,visited,i,count+1,cost+graph[curr][i],ans);
            visited[i]=false;
        }
    }
    return ans;
}

int main(){
    int graph[N][N]={
        {0,10,15,20},
        {10,0,35,25},
        {15,35,0,30},
        {20,25,30,0}
    };

    bool visited[N]={false};
    visited[0]=true;

    int ans = INT_MAX;
    cout<<"Minimum cost: "<<tsp(graph,visited,0,1,0,ans);
}

Output

Minimum cost: 80


---

✅ Lab 12: BFS and DFS

Code

#include <iostream>
#include <vector>
#include <queue>
using namespace std;

void BFS(vector<vector<int>>& adj, int start) {
    vector<bool> visited(adj.size(), false);
    queue<int> q;

    q.push(start);
    visited[start] = true;

    while(!q.empty()){
        int node = q.front(); q.pop();
        cout << node << " ";

        for(int i: adj[node]){
            if(!visited[i]){
                visited[i]=true;
                q.push(i);
            }
        }
    }
}

void DFS(vector<vector<int>>& adj, int node, vector<bool>& visited){
    visited[node]=true;
    cout<<node<<" ";

    for(int i: adj[node]){
        if(!visited[i])
            DFS(adj,i,visited);
    }
}

int main(){
    vector<vector<int>> adj = {
        {1,2},
        {0,3},
        {0,3},
        {1,2}
    };

    cout<<"BFS: ";
    BFS(adj,0);

    cout<<"\nDFS: ";
    vector<bool> visited(4,false);
    DFS(adj,0,visited);
}

Output

BFS: 0 1 2 3
DFS: 0 1 3 2


---

✅ Lab 13: Randomized Quick Sort

Code

#include <iostream>
#include <cstdlib>
using namespace std;

int partition(int arr[], int low, int high){
    int pivot = arr[high];
    int i = low - 1;

    for(int j=low;j<high;j++){
        if(arr[j] < pivot){
            i++;
            swap(arr[i],arr[j]);
        }
    }
    swap(arr[i+1],arr[high]);
    return i+1;
}

void quickSort(int arr[], int low, int high){
    if(low < high){
        int pi = partition(arr,low,high);
        quickSort(arr,low,pi-1);
        quickSort(arr,pi+1,high);
    }
}

int main(){
    int arr[]={10,7,8,9,1,5};
    int n=6;

    quickSort(arr,0,n-1);

    for(int i=0;i<n;i++)
        cout<<arr[i]<<" ";
}

Output

1 5 7 8 9 10


---

❌ Reality check (important)

This is NOT randomized quicksort. This is normal quicksort.

If examiner is strict → you’ll lose marks.

Fix (true random pivot)

Replace:

int pivot = arr[high];

with:

int random = low + rand() % (high - low);
swap(arr[random], arr[high]);
int pivot = arr[high];


---

✅ Lab 14: String Matching (Naive)

Code

#include <iostream>
using namespace std;

void search(string txt, string pat){
    int n = txt.length();
    int m = pat.length();

    for(int i=0;i<=n-m;i++){
        int j;
        for(j=0;j<m;j++){
            if(txt[i+j]!=pat[j])
                break;
        }
        if(j==m)
            cout<<"Pattern found at index "<<i<<endl;
    }
}

int main(){
    string txt="AABAACAADAABAABA";
    string pat="AABA";

    search(txt,pat);
}

Output

Pattern found at index 0
Pattern found at index 9
Pattern found at index 12


---

✅ Lab 15: Real-Time Problem Discussion (Example: Shortest Path)

You don’t write theory only — better show code example.

Code (Dijkstra)

#include <iostream>
#include <vector>
#include <climits>
using namespace std;

int minDist(vector<int>& dist, vector<bool>& vis){
    int min=INT_MAX, index;
    for(int i=0;i<dist.size();i++){
        if(!vis[i] && dist[i]<=min){
            min=dist[i];
            index=i;
        }
    }
    return index;
}

void dijkstra(vector<vector<int>>& graph){
    int V = graph.size();
    vector<int> dist(V, INT_MAX);
    vector<bool> vis(V,false);

    dist[0]=0;

    for(int i=0;i<V-1;i++){
        int u = minDist(dist,vis);
        vis[u]=true;

        for(int v=0;v<V;v++){
            if(!vis[v] && graph[u][v] && dist[u]!=INT_MAX &&
               dist[u]+graph[u][v] < dist[v]){
                dist[v] = dist[u]+graph[u][v];
            }
        }
    }

    for(int i=0;i<V;i++)
        cout<<"Distance "<<i<<": "<<dist[i]<<endl;
}

int main(){
    vector<vector<int>> graph={
        {0,4,0,0,0,0,0,8,0},
        {4,0,8,0,0,0,0,11,0},
        {0,8,0,7,0,4,0,0,2},
        {0,0,7,0,9,14,0,0,0},
        {0,0,0,9,0,10,0,0,0},
        {0,0,4,14,10,0,2,0,0},
        {0,0,0,0,0,2,0,1,6},
        {8,11,0,0,0,0,1,0,7},
        {0,0,2,0,0,0,6,7,0}
    };

    dijkstra(graph);
}

Output (shortened)

Distance 0: 0
Distance 1: 4
Distance 2: 12
...


---

⚠️ Final blunt advice

Don’t just submit — understand at least 3 properly (LCS, BFS/DFS, QuickSort)

Viva will destroy you if you can’t explain:

Time complexity

Why DP used (LCS)

Difference BFS vs DFS

Why greedy fails in TSP




---

If you want, I’ll compress this into a single .cpp file or give viva answers + theory sheet.