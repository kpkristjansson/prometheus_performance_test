# prometheus_performance_test

## Avalanche
Prometheus/OpenMetrics endpoint series generator for load testing.  
https://github.com/open-fresh/avalanche

## avalanche.yaml

*  Creates a deployment running a few replicas of avalanche.  
*  Creates a service for avalanche.  
*  Creates a servicemonitor (prometheus-operator CRD) - https://github.com/helm/charts/tree/master/stable/prometheus-operator

#### Configuration
Check out the container `args` before running `kubectl`  
Then run: 

```bash
kubectl apply -f avalanche.yaml
```

You should see the ServiceMonitoring appear in the Prometheus Service Discovery tab and your prometheus instance should be receiving the new metrics.

I recommend using the Prometheus Benchmark dashboard, from grafana.com, to review the load on Prometheus.  Like this one: https://grafana.com/dashboards/9761  

You might have a little chicken or the egg problem though :)
  
