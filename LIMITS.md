# Request Limits

CoinFLEX's application programming interface (API) allows our clients to access and control their accounts or view our market data using custom-written software. To protect the performance of the system, we impose certain limits:

| Metric                  |                            Limit |
|:------------------------|---------------------------------:|
| Open orders             |                   1,000 per user |
| Authentication attempts |          1,000 per hour per user |
| Order placements*       |          200 per second per user |
| Information requests†   |    10 per 10 seconds per session |
| Records requests‡       |         30 per 1 minute per user |
| Conversion requests     |         1 per 5 seconds per user |

\* "Order placements" also include order cancellations and market order estimates. This is for websockets. Via REST, the limit is 300 per 10 second window.

† "Information requests" include balance inquiries, open order listings, and trade volume inquiries.

‡ "Records requests" pertain to requests for historical records, such as past trades.
