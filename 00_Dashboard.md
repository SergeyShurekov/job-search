## 📊 Активные вакансии

```dataview
TABLE role, status, priority, date_applied
FROM "04_JobSearch/10_Companies"
WHERE status != "rejected" AND status != "closed_vacancy_removed" AND status != "passed"
SORT priority DESC, date_applied DESC
```

## 🔥 Высокий приоритет

```dataview
LIST FROM "04_JobSearch/10_Companies"
WHERE priority = "high" AND status != "rejected" AND status != "closed_vacancy_removed" AND status != "passed"
```

## ⏰ Напомнить на этой неделе

```dataview
LIST FROM "04_JobSearch/10_Companies"
WHERE next_followup <= date(now) + dur(7 days) AND status != "rejected" AND status != "closed_vacancy_removed" AND status != "passed"
```