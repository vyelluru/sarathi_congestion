# sarathi_congestion
Sarathi-Serve's chunk size is set as a fixed configuration parameter at launch time. It's a hyperparameter you tune before serving, not something the system adjusts at runtime. So when the system gets congested:

There's no feedback loop — it doesn't detect that TPOT (time per output token) is degrading and respond
The scheduler keeps processing prefill chunks at the same fixed size regardless of how badly decode latency is suffering
Requests just queue up, and TPOT violations accumulate


Normal TCP reacts after packet loss happens
This system wants to be proactive — detecting that TPOT violations are about to occur and backing off before they happen (like predictive congestion control, similar to BBR or QUIC-style approaches)