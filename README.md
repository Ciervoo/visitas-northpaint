# Visitas — North Paint

App de registro de visitas comerciales para el equipo de North Paint.

## Setup Supabase

Antes de usar la app, ejecutá este SQL en el **Editor SQL** de tu proyecto Supabase:

```sql
CREATE TABLE IF NOT EXISTS visitas (
  id           bigint PRIMARY KEY,
  vendedor     text NOT NULL,
  nombre_taller text NOT NULL,
  dueno        text,
  telefono     text,
  direccion    text,
  fecha        date NOT NULL,
  marca        text,
  tiene_cabina boolean,
  laboratorio_color boolean,
  tamano       text,
  notas        text,
  created_at   timestamptz DEFAULT now()
);

-- Política de acceso abierto (igual que las otras tablas)
ALTER TABLE visitas ENABLE ROW LEVEL SECURITY;
CREATE POLICY "allow_all" ON visitas FOR ALL USING (true) WITH CHECK (true);
```

## Deploy

1. Pusheá a `main` → Vercel deploya automáticamente.
