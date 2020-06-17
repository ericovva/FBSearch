# Поиск людей graphQL:

* текст для поиска указывается в variables -> text
* лимиты count
* пагинация (в ответе приходит параметр end_cursor) его нужно отправить при следующем запросе в variables в параметре cursor

```
curl --location --request POST 'https://www.facebook.com/api/graphql/' \
--header 'authority: www.facebook.com' \
--header 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.97 Safari/537.36' \
--header 'content-type: application/x-www-form-urlencoded' \
--header 'origin: https://www.facebook.com' \
--header 'referer: https://www.facebook.com/search/people?q=%D0%B2%D0%BE%D0%BB%D0%B3%D0%BE%D0%B3%D1%80%D0%B0%D0%B4' \
--header 'authorization: Bearer EAAD7MJZAn7Q4BAIh3nFjs4hahH8rJ3wJtDvOVGI4mARFfXb6E5EdbE8YsQNnZBrkOsAocW5F1zBaRvJWuOKtB05kh2c5oEpgiu38gFEbJfLBdMr4u8yotaAKy4PErUPyygM0QbWFpZAqHC21CVj55K2rRPTVOdK4VNRIf9wjwMUGZBmEZA859PFt6ImZBBvzSKSoCF7d6sz6ZB4jhMst6xfuO00y557e8YbaczpZAfmA7wZDZD' \
--data-urlencode 'fb_dtsg=AQGoVREVc1Oc:AQEaU1GNMP0N' \
--data-urlencode 'variables={"UFI2CommentsProvider_commentsKey":"CometSearchResultsInitialResultsQuery","allow_streaming":false,"args":{"callsite":"COMET_GLOBAL_SEARCH","config":{"bootstrap_config":null,"exact_match":false,"high_confidence_config":null,"watch_config":null},"context":{"bsid":"fb589925-db0d-40b8-9a61-274b3e758fdd","tsid":"0.4505627899089055"},"experience":{"fbid":null,"grammar_bqf":null,"role":null,"type":"PEOPLE_TAB"},"filters":[],"text":"волосы"},"count":5,"displayCommentsContextEnableComment":false,"displayCommentsContextIsAdPreview":false,"displayCommentsContextIsAggregatedShare":false,"displayCommentsContextIsStorySet":false,"displayCommentsFeedbackContext":null,"feedLocation":"SEARCH","feedbackSource":23,"fetch_filters":true,"focusCommentID":null,"isComet":true,"privacySelectorRenderLocation":"COMET_STREAM","renderLocation":null,"scale":2,"stream_initial_count":0,"useDefaultActor":false}' \
--data-urlencode 'doc_id=3094440570652798'
```

# Дополнительная фильтрация по Городу|Образованию|Работе

* Получить ID обьекта для фильтрации 
* filterID
Город: 
Z3NxZjp7IjAiOiJicm93c2VfaW5zdGFudF9maWx0ZXIiLCIxIjoia2V5d29yZHNfdXNlcnMoXHUwMDI1RDBcdTAwMjU5OFx1MDAyNUQwXHUwMDI1QjNcdTAwMjVEMFx1MDAyNUJFXHUwMDI1RDFcdTAwMjU4MFx1MDAyNUQxXHUwMDI1OEMpIiwiMyI6IjI4YTkyYWQyLTE3ZmUtNDZlMy1iMmU1LWY4NzQ0MTNlZTg0YSIsImN1c3RvbV92YWx1ZSI6IkJyb3dzZVVzZXJzQ2l0eUluc3RhbnRGaWx0ZXJDdXN0b21WYWx1ZSJ9

Образование:
Z3NxZjp7IjAiOiJicm93c2VfaW5zdGFudF9maWx0ZXIiLCIxIjoia2V5d29yZHNfdXNlcnMoXHUwMDI1RDBcdTAwMjU5OFx1MDAyNUQwXHUwMDI1QjNcdTAwMjVEMFx1MDAyNUJFXHUwMDI1RDFcdTAwMjU4MFx1MDAyNUQxXHUwMDI1OEMpIiwiMyI6ImMzNzMzMzU0LTQyNjItNDJkNC04YzQyLWU0Y2YwZmE5ZWEyZCIsImN1c3RvbV92YWx1ZSI6IkJyb3dzZVVzZXJzU2Nob29sSW5zdGFudEZpbHRlckN1c3RvbVZhbHVlIn0=

Работа:
Z3NxZjp7IjAiOiJicm93c2VfaW5zdGFudF9maWx0ZXIiLCIxIjoia2V5d29yZHNfdXNlcnMoXHUwMDI1RDBcdTAwMjU5OFx1MDAyNUQwXHUwMDI1QjNcdTAwMjVEMFx1MDAyNUJFXHUwMDI1RDFcdTAwMjU4MFx1MDAyNUQxXHUwMDI1OEMpIiwiMyI6IjRhOGEzYjk4LTUyNWMtNDZmNS04OTQ2LWEzNGU5ODkwNjkyOSIsImN1c3RvbV92YWx1ZSI6IkJyb3dzZVVzZXJzRW1wbG95ZXJJbnN0YW50RmlsdGVyQ3VzdG9tVmFsdWUifQ==

* count лимиты
* пагинация аналогично по cursor

```
curl --location --request POST 'https://www.facebook.com/api/graphql/' \
--header 'authority: www.facebook.com' \
--header 'user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_4) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.97 Safari/537.36' \
--header 'content-type: application/x-www-form-urlencoded' \
--header 'origin: https://www.facebook.com' \
--header 'referer: https://www.facebook.com/search/people?q=%D0%98%D0%B3%D0%BE%D1%80%D1%8C' \
--header 'authorization: Bearer EAAD7MJZAn7Q4BAIh3nFjs4hahH8rJ3wJtDvOVGI4mARFfXb6E5EdbE8YsQNnZBrkOsAocW5F1zBaRvJWuOKtB05kh2c5oEpgiu38gFEbJfLBdMr4u8yotaAKy4PErUPyygM0QbWFpZAqHC21CVj55K2rRPTVOdK4VNRIf9wjwMUGZBmEZA859PFt6ImZBBvzSKSoCF7d6sz6ZB4jhMst6xfuO00y557e8YbaczpZAfmA7wZDZD' \
--data-urlencode 'fb_dtsg=AQEVPsb9581W:AQGaTN_19pgO' \
--data-urlencode 'variables={"count":8,"filterID":"Z3NxZjp7IjAiOiJicm93c2VfaW5zdGFudF9maWx0ZXIiLCIxIjoia2V5d29yZHNfdXNlcnMoXHUwMDI1RDBcdTAwMjU5OFx1MDAyNUQwXHUwMDI1QjNcdTAwMjVEMFx1MDAyNUJFXHUwMDI1RDFcdTAwMjU4MFx1MDAyNUQxXHUwMDI1OEMpIiwiMyI6IjczNGYzNmI0LWY4NTMtNDk1Ni05ZmUzLWQ2MTRlOTRjYTRiNCIsImN1c3RvbV92YWx1ZSI6IkJyb3dzZVVzZXJzQ2l0eUluc3RhbnRGaWx0ZXJDdXN0b21WYWx1ZSJ9","profile_picture_size":null,"query":"new"}' \
--data-urlencode 'doc_id=2662288270522393'
```

Получить результат из поля `data.node.filter_values.edges.0.node.filterValue` вида
"{"name":"users_employer","args":"362252433862064"}"

и указать его в исходном запросе поиска в поле filters AS IS:
filters: ["{"name":"users_employer","args":"362252433862064"}"]
