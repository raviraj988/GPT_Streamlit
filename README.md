Show that for a continuous attribute $X$, the only split values we need to check to determine a split with max $IG(X)$ lie between points with different labels. (Hint: consider the following setting for $X$: there is a candidate split point $S$ in the middle of $N$ examples with the same label. To the left of $S$ are $n$ such examples. To the left of $N$, there are $L_0$ examples with label negative and $L_1$ positive, and likewise $(M_0, M_1)$ to the right. Express the information gain of $S$ as a function of $n$. Then show that this function is maximized either when $n=0$ or $n=N$ with all else constant.) (30 points)

$$ IG(X) = H(D) - \left( \frac{N}{N+M} \right) H(N) - \left( \frac{M}{N+M} \right) H(M) $$

$$ IG(X|S=S_n) = H(D) - \left( \frac{n}{N+M} \right) H(n,0,0,n_{L_1}) - \left( \frac{N-n+M}{N+M} \right)H(N-n,L_0,L_1,M-M_1,M_0)) $$

$$ IG(X|S=S_n)=H(D)-\left(\frac{n}{N+M}\right)\left(-\sum_{i=0}^{1}\frac{n_{L_i}}{n}\log_2\frac{n_{L_i}}{n}\right)- \left(\frac{N-n+M}{N+M}\right)\left(-\sum_{i=0}^{1}\frac{(L_i+n_{L_i})+(M_i+n_{L_i})}{N-n+M}\log_2\frac{(L_i+n_{L_i})+(M_i+n_{L_i})}{N-n+M}\right). $$
