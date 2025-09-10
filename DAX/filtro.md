# 🧮 Medida: **Perda_TOTAL**

## 📌 Objetivo
Calcular o **total de perdas** considerando apenas os tipos **Validade**, **Avaria** e **Fábrica**,  
ignorando todos os filtros aplicados na página.

---

## 📄 Código DAX

```DAX
Perda_TOTAL =
CALCULATE (
    SUM ( TROCAS_5[$ Perda] ),
    REMOVEFILTERS (), -- remove todos os filtros ativos na página
    TROCAS_5[Tipo] IN { "Validade", "Avaria", "Fábrica" } -- mantém apenas os tipos desejados
)

