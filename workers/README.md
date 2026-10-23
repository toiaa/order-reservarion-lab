# workers/

Background processes, run as separate Compose services (not inside the Flask container).

- `outbox_publisher.py` — Step 7. Polls the `outbox` table, publishes to Kafka, marks rows
  published.
- `inventory_consumer.py` — Step 8. Kafka consumer group that reserves stock. Commit the
  offset only after the DB write succeeds; guard against duplicates with a unique
  constraint on `order_id`.
- `celery_app.py` — Step 9/10. Celery app + tasks (notifications) + Beat schedule
  (reservation expiry).
