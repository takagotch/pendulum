### pendulum
---
https://github.com/sdispater/pendulum

```py
import pendulum
now_in_paris = pendulum.now('Europe/Paris')
now_in_paris

now_in_paris.in_timezone('UTC')

tomorrow = pendulum.now().add(days=1)
last_week = pendulum.now().subtract(weeks=1)

past = pendulum.now().subtract(minutes=2)
past.diff_for_humans()
'2 minutes ago'

delta = past - last_week
delta.hours

dleta.in_words(locale='en')

pendulum.datetime(2013, 3, 31, 2, 30, tz='Europe/Paris')
just_before = pendulum.datetime(2013, 3, 31, 1, 59, 59, 999999, tz='Europe/Paris')
just_before.add(microseconds=1)

arrow.get('2016-1-17')
pendulum.parse('2016-1-17')
arrow.get('20160413')
pendulum.parse('20160413')
arrow.get('2016-W07-5')
just_before = arrow.Arrow(2013, 3, 31, 1, 59, 59, 99999, 'Europe/Paris')
(just_after.to('utc') - just_before.to('utc')).total_seconds()

just_before = pendulum.datetime(2013, 3, 31, 1, 59, 59, 999999, 'Europe/Paris')
just_after = just_before.add(microseconds=1)


from pendulum import DateTime
from sqlite3 import register_adapter
register_adapter(DateTime, lambda val: val.isoformat(' '))

import MySQLdb.converters
import pymysql.coverters

from pendulum import DateTime

MySQLdb.converters.conversions[DateTime] = MySQLdb.converters.DateTime2literal
pymysql.converters.conversions[DateTime] = pymysql.converters.escape_datetime

from django.db.models import DateTimeField as BaseDateTimeField
from pendulum import DateTime

class DateTimeField(BaseDateTimeField):
  def value_to_string(self, obj):
    val = self.value_from_object(obj)
    
    if isinstance(value, DateTime):
      return value.to_datetime_string()
      
    return '' if val is None else val.isoformat()

```

```sh
git cloen git@github.com:sdispater/pendulum.git
poetry install
./clock locale create <your-locale>
```

```
```

