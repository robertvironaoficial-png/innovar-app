# Handover 02 — Inventario Supabase y tablas clave

## Propósito

Este documento resume el inventario técnico de Supabase ya revisado en modo lectura. La siguiente IA debe usarlo como punto de partida y profundizar carpeta por carpeta.

## Proyecto Supabase

- Project ID: `xdzbjptozeqcbnaqhtye`
- Nombre observado: `Innovar CRM`

## Identidad, seguridad y auditoría

### `profiles`
Columnas relevantes:
- `id`
- `email`
- `full_name`
- `role`
- `is_active`
- `avatar_url`
- `notification_preferences`
- `created_at`
- `updated_at`

Roles observados:
- `admin`
- `comercial`
- `diseno`
- `produccion`

### `audit_log`
- `id`
- `user_id`
- `action`
- `table_name`
- `record_id`
- `old_data`
- `new_data`
- `created_at`

### `audit_logs`
- `id`
- `userId`
- `userName`
- `action`
- `tableName`
- `recordId`
- `changesSummary`
- `ipAddress`
- `userAgent`
- `timestamp`

Pendiente: investigar por qué coexisten dos tablas de auditoría.

---

## Clientes, leads y cotizaciones

### `clients`
- `id`
- `name`
- `whatsapp_phone`
- `email`
- `address`
- `services`
- `status`
- `urgency`
- `assigned_to`
- `assigned_at`
- `converted_to_id`
- `city`
- `lead_score`
- `lead_score_details`
- `lead_scored_at`
- `created_at`
- `updated_at`
- `deleted_at`

Observación: `clients` parece cubrir tanto clientes consolidados como solicitudes/leads.

### `quotations`
- `id`
- `client_id`
- `total_amount`
- `status`
- `is_locked`
- `notes`
- `subtotal`
- `discount_type`
- `discount_value`
- `transport_cost`
- `version_number`
- `parent_quotation_id`
- `is_historical_copy`
- `valid_until`
- `created_at`
- `updated_at`
- `deleted_at`

Estados observados:
- `draft`
- `sent`
- `approved`
- `rejected`

### `quotation_items`
- `id`
- `quotation_id`
- `description`
- `quantity`
- `unit_price`
- `product_category`
- `configuration`
- `created_at`
- `updated_at`

Observación previa: existían cotizaciones, pero `quotation_items` no mostraba registros durante la revisión inicial.

---

## Proyectos y postventa

### `projects`
- `id`
- `client_id`
- `approved_quotation_id`
- `name`
- `work_type`
- `status`
- `designer_id`
- `tracking_token`
- `notes`
- `total_amount`
- `advance_amount`
- `client_approved_at`
- `client_approval_notes`
- `created_by`
- `design_deadline`
- `design_delivered_at`
- `initial_measurements`
- `design_3d_files`
- `despiece_files`
- `estimated_install_date`
- `scheduled_install_date`
- `install_duration_days`
- `delivered_at`
- `modelado_approved_at`
- `renders_approved_at`
- `render_revision_number`
- `modelado_revision_number`
- `quotation_pdf_url`
- `is_archived`
- `skip_design_process`
- `data_origin`
- `accounting_closure_id`
- `created_at`
- `updated_at`
- `deleted_at`

`work_type`:
- `cocina`
- `closet`
- `puertas`
- `centro_tv`
- `otro`

`status`:
- `contacto`
- `cotizacion_aprobada`
- `en_diseno`
- `aprobacion_final`
- `en_produccion`
- `listo_instalacion`
- `entregado`

### Tablas auxiliares de proyectos

#### `project_photos`
- `id`
- `project_id`
- `stage`
- `photo_url`
- `caption`
- `created_at`

#### `warranties`
- `id`
- `project_id`
- `client_id`
- `warranty_months`
- `starts_at`
- `expires_at`
- `status`
- `notes`

#### `warranty_claims`
- `id`
- `warranty_id`
- `reported_at`
- `description`
- `severity`
- `status`
- `resolved_at`
- `resolution_notes`
- `assigned_to`

#### `satisfaction_surveys`
- `id`
- `project_id`
- `client_id`
- `sent_at`
- `responded_at`
- `rating_overall`
- `rating_quality`
- `rating_punctuality`
- `rating_service`
- `comments`
- `would_recommend`
- `status`

---

## Agenda, citas y tareas

### `tasks`
- `id`
- `project_id`
- `assigned_to`
- `title`
- `description`
- `status`
- `priority`
- `due_date`
- `client_id`
- `appointment_type`
- `time_slot`
- `created_by`
- `task_category`
- `kanban_order`
- `completed_at`
- `tags`
- `estimated_hours`
- `actual_hours`

Estados:
- `pendiente`
- `en_progreso`
- `en_revision`
- `bloqueado`
- `completado`
- `cancelado`

Categorías:
- `cita`
- `operativa`
- `diseno`
- `produccion`
- `administrativa`
- `seguimiento`

Observación: la tabla `tasks` parece sostener tanto tareas como citas.

### Tablas auxiliares

#### `availability_slots`
- `id`
- `staff_id`
- `date`
- `start_time`
- `end_time`
- `is_booked`
- `task_id`

#### `task_comments`
- `id`
- `task_id`
- `author_id`
- `content`

#### `task_attachments`
- `id`
- `task_id`
- `uploaded_by`
- `file_name`
- `file_url`
- `file_size`
- `mime_type`

#### `calendar_sync_queue`
- `id`
- `task_id`
- `calendar_id`
- `google_event_id`
- `action`
- `status`
- `payload`
- `error_msg`
- `created_at`
- `synced_at`

---

## Finanzas

### `payments`
- `id`
- `project_id`
- `amount`
- `payment_method`
- `payment_type`
- `received_at`
- `notes`
- `registered_by`
- `receipt_url`
- `client_id`

### `expenses`
- `id`
- `project_id`
- `category`
- `amount`
- `expense_date`
- `receipt_url`
- `description`
- `registered_by`
- `approved_by`
- `approval_status`
- `client_id`
- `notes`

### `accounting_closures`
- `id`
- `project_id`
- `closed_by`
- `closure_date`
- `total_income`
- `total_expenses`
- `net_profit`
- `profit_margin`
- `notes`
- `status`

---

## Configuración y catálogos

### `materials`
- `id`
- `category`
- `name`
- `description`
- `photoUrl`
- `price`
- `unit`
- `active`
- `sortOrder`

### `pricing_catalog`
- `id`
- `code`
- `name`
- `category`
- `description`
- `value`
- `unit`
- `previousValue`
- `lastUpdated`

### `holidays`
- `id`
- `date`
- `name`
- `year`

---

## Notificaciones, colas y automatizaciones

### `notifications`
- `id`
- `user_id`
- `title`
- `body`
- `is_read`
- `related_table`
- `related_id`
- `notification_type`
- `priority`
- `action_url`

### `notification_queue`
- `id`
- `event_type`
- `event_reference_id`
- `entity_type`
- `entity_reference_id`
- `recipient_type`
- `recipient_reference_id`
- `recipient_name`
- `recipient_phone`
- `channel`
- `provider`
- `template_name`
- `template_language`
- `template_parameters`
- `payload`
- `status`
- `delivery_status`
- `provider_message_id`
- `provider_response`
- `webhook_payload`
- `error_message`
- `failed_reason`
- `attempt_count`

### `whatsapp_message_log`
- `id`
- `phone`
- `message`
- `event_type`
- `related_table`
- `related_id`
- `sent_at`
- `status`
- `error_msg`

### `meta_whatsapp_status_events`
- `id`
- `provider_message_id`
- `recipient_id`
- `status`
- `status_timestamp`
- `raw_payload`
- `errors`
- `conversation`
- `pricing`
- `created_at`

### `pdf_generation_queue`
- `id`
- `quotation_id`
- `status`
- `pdf_url`
- `error_msg`
- `requested_at`
- `completed_at`
- `requested_by`

### `scheduled_job_log`
- `id`
- `job_name`
- `started_at`
- `finished_at`
- `status`
- `rows_affected`
- `error_msg`

Riesgo detectado: `scheduled_job_log` aparece con RLS desactivado.

---

## Diccionarios internos

### `bucket_dictionary`
- `bucket_id`
- `description`
- `access_level`
- `created_at`

### `system_dictionary`
- `id`
- `category`
- `name`
- `description`
- `trigger_event`
- `status`
- `created_at`
- `updated_at`

Categorías posibles:
- `BUCKET`
- `EDGE_FUNCTION`
- `DB_TRIGGER`
- `CRON_JOB`
