FROM hashicorp/terraform:latest AS builder

# Копируем /bin/terraform в промежуточный слой
RUN mkdir /output && cp /bin/terraform /output/terraform

# Используем scratch слой для извлечения файла
FROM scratch AS export-stage

# Копируем файл из промежуточного слоя
COPY --from=builder /output/terraform /terraform