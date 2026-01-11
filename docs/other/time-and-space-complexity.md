# 时间和空间复杂度

## 时间复杂度

**时间复杂度** 是一个函数，也是一个算法执行基本运算的次数，用来衡量一个算法在时间上的效率。

一般而言，我们用大 O 符号来表示时间复杂度。在书写时，省略常数，保留最高阶项。例如在数据规模为 $n$ 的情况，有一个算法的执行基本运算的次数为 $n + \log n$[^1]，则该算法的时间复杂度一般写作 $O(n)$。

### 计算

先看一个简单的例子：

!!! example "例 1"

    ``` cpp
    int solve(int n){
        int cnt = 0;
        for(int i = 1; i <= n; i++)
            for(int j = 1; j <= i; j++)
                cnt++;
        return cnt;
    }
    ```

执行一次例 1 的算法会有

$$
\sum^n_{i=1} i
$$

次基本运算，由等差数列求和公式，他的结果为 $\dfrac{n(n + 1)}{2}$，所以该算法时间复杂度为 $O(n^2)$。

!!! example "例 2"

    ``` cpp
    const int N = 1005;
    vector<int> g[N];
    int a[N], dp[N][N], tmp[N];
    int n, m; // 节点数 n，容量 m，每个节点的重量为 1
    void dfs(int u){
        for(int i = 1; i <= m; i++)
            dp[u][i] = a[u];
        for(auto v : g[u]){
            dfs(v);
            for(int i = 1; i <= m; i++)
                tmp[i] = dp[u][i];
            for(int i = 1; i <= m; i++)
                for(int j = 0; j < i; j++)
                    dp[u][i] = max(dp[u][i], tmp[i - j] + dp[v][j]);
        }
    }
    ```

例 2 实际上是一个树形背包的代码，显然，它的时间复杂度为 $O(nm^2)$。但是，因为在以 $u$ 为根的子树上做树形背包容量最大为这棵子树的节点数，所以我们可以进行优化，那么优化后的时间复杂度为多少呢？其实是 $O(nm)$，证明如下。