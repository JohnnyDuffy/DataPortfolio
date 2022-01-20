Here I took publicly available data from a Bike share company, and looked to answer a few questions:

  * How do customers with annual memberships differ from one-time users?
  * What kind of trends do we notice in customer behaviour?

After cleaning the data, I wanted to see breakdown how customers are using the bikes. 
This R script compares the average ride durations of casual users and users with the annual membership:
```
data %>%
  mutate('duration' = (ended_at - started_at)) %>%
  group_by(member_casual) %>%
  summarise(mean(duration))
```
From this we get the following results:
```
  member_casual `mean(duration)`
  <chr>         <drtn>
1 casual        2597.2869 secs
2 member         714.1319 secs
```
As we can see, the casual rider on average uses the bike for much longer than the rider with the annual membership. But how does this breakdown over the week?


<p align="center">
<img src="resources/BikeDuration.png" width="900" height="610">
</p>
