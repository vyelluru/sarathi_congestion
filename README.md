# sarathi_congestion
Sarathi-Serve's chunk size is set as a fixed configuration parameter at launch time. It's a hyperparameter you tune before serving, not something the system adjusts at runtime. So it might not be the optimal chunk size based on your workload, requirements, and SLO.

This tool is a fine-grained controller over the chunk size based on the tradeoffs you are willing to accept.
