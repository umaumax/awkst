#!/usr/bin/awk -f
BEGIN {
  cnt = 0
  sum = 0
  min = "dummy"
  max = "dummy"
}
$1 ~ /^[0-9]*(\.[0-9]*)?$/ {
  v = $1
  vals[cnt] = v
  min = v < min || min == "dummy" ? v : min
  max = v > max || max == "dummy" ? v : max
  sum += v
  cnt++
}
END {
  ave = sum / cnt
  tmp=0.0
  for(i in vals)tmp+=(vals[i]-ave)^2
  variance = tmp/cnt
  covariance = sqrt(variance)
  printf "# %4s, %8s, %8s, %8s, %8s, %8s\n", "cnt", "sum", "ave", "min", "max", "cov"
  printf "%6d, %8.4f, %8.4f, %8.4f, %8.4f, %8.4f\n", cnt, sum, ave, min, max, covariance
}


