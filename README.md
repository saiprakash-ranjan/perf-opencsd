# perf-opencsd
perf binary static linked with opencsd

## Reference:

https://people.linaro.org/~leo.yan/opencsd_db410c/

## Sample usage:

On older kernels(4.9):

```
perf record -e cs_etm/timestamp,@6047000.etf/ --per-thread ls
perf report -D -i perf.data | grep Timestamp
```

On newer kernels(5.4+):

```
perf record -e cs_etm/timestamp,cycacc,@tmc_etf0/ -a -- ls
perf report -D -i perf.data | grep Timestamp
```
