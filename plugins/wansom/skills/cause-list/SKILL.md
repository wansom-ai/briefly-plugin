---
name: cause-list
description: Look up Kenya cause lists with Wansom AI — which judge and court room hear which matters, by court type, station and dates.
argument-hint: <court> <station> [start date] [end date]
disable-model-invocation: true
---

# Kenya cause list: $ARGUMENTS

1. Call `kenya_cause_list` with the `court` (High Court, Magistrate's Court, Environment and Land Court, Employment and Labour Relations Court, Small Claims Court), the `station`, and optional `start_date` / `end_date` (YYYY-MM-DD, at most 14 days; by default the last 7 days).
2. If the tool returns options instead of a list, show them and ask the user to pick, then call it again.
3. If the user is looking for a particular matter, find it by file number or party name and give its date, time, judge, court room and the virtual court link when there is one. Otherwise summarise by day and judge.
4. Say the information comes from Kenya Law's published cause lists and that listings can change — the user should confirm with the registry for anything critical.
