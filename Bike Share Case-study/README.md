Here I took publicly available data from a Bike share company, and looked to answer a few questions:

  * How do customers with annual memberships differ from one-time users?
  * What kind of trends do we notice in customer behaviour?


```
M %>%
  mutate('duration' = (ended_at - started_at)) %>%
  group_by(member_casual) %>%
  summarise(mean(duration))


  member_casual `mean(duration)`
  <chr>         <drtn>
1 casual        2597.2869 secs
2 member         714.1319 secs
```
