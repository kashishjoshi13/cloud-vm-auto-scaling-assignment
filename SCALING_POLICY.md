# Auto Scaling Policy Details

## Policy Type
Target Tracking Scaling Policy

---

## Metric Used
EC2 Average CPU Utilization

---

## Target Value
60%

---

## Scaling Behavior

If CPU > 60%:
- New EC2 instance launched
- Load Balancer automatically distributes traffic

If CPU < 60%:
- Extra instances terminated gradually
- Cost optimized

---

## Advantages
- Automatic resource adjustment
- High availability
- Cost efficiency
- No manual intervention required