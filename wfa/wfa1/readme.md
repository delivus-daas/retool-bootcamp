
스크린샷 추가

# 목표
# API 스펙
# Tips
## CODE

중기예보는 0600시, 1800시에 업데이트 된다. 
api 호출시 queryparam에 tmFc로 발표시간을 전달한다.

Retool의 [transformer](https://docs.retool.com/queries/guides/transformers)를 사용해
현재시간이 6시 이전이면 전날 1800,
6시 이후, 18시 이전이면 당일 0600,
18시 이후라면 당일 1800 으로 설정한다.

```
let current_time = moment().format('HHMM');
let current_date = moment().format('YYYYMMDD')
let yesterdate = moment().subtract(1, 'day').format('YYYYMMDD')

if (current_time < '0600' ){
  return yesterdate + "1800"
} else if ( current_time > '1801') {
  return current_date + "1800"
} else {
  return current_date + "0600"
}
```

## UI Component
## ETC
