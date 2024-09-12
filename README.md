## Information Gain for Continuous Attribute Split

To show that for a continuous attribute \(X\), the only split values we need to check to determine a split with max \(IG(X)\) lie between points with different labels, consider the following setting:

- There is a candidate split point \(S\) in the middle of \(N\) examples with the same label.
- To the left of \(S\) are \(n\) such examples.
- To the left of \(N\), there are \(L_0\) examples with label negative and \(L_1\) positive.
- Likewise, \((M_0, M_1)\) to the right.

### Information Gain Calculation

The information gain \(IG(S)\) is given by:

\[ IG(S) = H(D) - \left(\frac{|D1|}{|D|}\right) H(D1) - \left(\frac{|D2|}{|D|}\right) H(D2) \]

Where \(H(X)\) is the entropy:

\[ H(X) = - \sum (p_i \log(p_i)) \]

For the split \(S\):

\[ H(X/S=S1) = - \sum \left(\frac{n_i}{N_i} \log\left(\frac{n_i}{N_i}\right)\right) \]

Thus, the information gain \(IG(S=S1)\) is:

\[ IG(S=S1) = H(X) - P(S=S1) H(X/S=S1) - P(S \neq S1) H(X/S \neq S1) \]

Substituting the values:

\[ IG(S=S1) = -\left(\frac{L_0}{L_0+L_1}\right) \log\left(\frac{L_0}{L_0+L_1}\right) - \left(\frac{L_1}{L_0+L_1}\right) \log\left(\frac{L_1}{L_0+L_1}\right) \]

\[ + \left(\frac{n+N}{N+M}\right) \left[\frac{n}{N} \log\left(\frac{n}{N}\right) + \frac{N-n}{N} \log\left(\frac{N-n}{N}\right)\right] \]

\[ + \left(\frac{M}{N+M}\right) \left[\frac{M_0}{M} \log\left(\frac{M_0}{M}\right) + \frac{M_1}{M} \log\left(\frac{M_1}{M}\right)\right] \]

### Derivative with Respect to \(n\)

Taking the derivative of \(IG(S=S1)\) with respect to \(n\):

\[ \frac{d}{dn} [IG(S=S1)] = \frac{d}{dn} \left\{\left(\frac{n+N}{N+M}\right) \left[\frac{n}{N} \log\left(\frac{n}{N}\right) + \frac{N-n}{N} \log\left(\frac{N-n}{N}\right)\right]\right\} \]

Let \(p = \frac{n}{N}\):

\[ \frac{d}{dp} \left[-p \log(p) - (1-p) \log(1-p)\right] = \frac{d}{dp} \left[-p \log(p) - \log(1-p) + p \log(1-p)\right] \]

### Conclusion

The function is maximized either when \(n = 0\) or \(n = N\) with all else constant.
