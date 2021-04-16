# Datalist.js

## Datalist.js là gì?

datalist.js là một thư viện dùng để hiển thị dữ liệu dạng list JSON hoặc [dữ liệu dạng findDataList](https://quangkhoi1228.gitbook.io/guide/shinobi-js-core/gioi-thieu-shinobi-js-core#du-lieu-dang-finddatalist) lên giao diện, các dữ liệu này thể hiện trên giao diện theo dạng các phần tử HTML lặp lại 1 cấu trúc giống như 1 list, 1 table hay vòng lặp,...

![V&#xED; d&#x1EE5; v&#x1EC1; c&#xE1;c element HTML d&#x1EA1;ng l&#x1EB7;p &#x111;i l&#x1EB7;p l&#x1EA1;i](../.gitbook/assets/image%20%2837%29.png)

## Yêu cầu

### CSS

```css
@keyframes spinAround {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(359deg);
    }
}

@keyframes spinAround {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(359deg);
    }
}

.table-pagination {
    margin-top: 0.75rem;
    margin-bottom: 0.75rem;
    padding: 0.75rem;
    display: flex;
    justify-content: flex-end;
}

.table-pagination .select-record-per-page-container,
.table-pagination .select-page-container {
    display: flex;
    padding: 0;
    margin-left: 2rem;
}

.table-pagination .select-page-container {
    display: flex;
    padding: 0;
    margin-left: 2rem;
}

.table-pagination .table-pagination-row-total,
.table-pagination .table-pagination-page-total,
.table-pagination .shinobi-pagination-curpage,
.table-pagination .shinobi-recordperpage {
    font-weight: 700;
}

.table-pagination .table-pagination-row-total,
.table-pagination .table-pagination-page-total,
.table-pagination .shinobi-pagination-curpage {
    line-height: 1.75;
}

.table-pagination .table-pagination-label {
    margin-left: 0.5rem;
    margin-right: 0.5rem;
    line-height: 1.75;
}

.table-pagination .table-pagination-label:last-child {
    margin-right: 0;
}

.table-pagination .table-pagination-label:first-child {
    margin-left: 0;
}

.table-pagination .shinobi-pagination-prev,
.table-pagination .shinobi-pagination-next {
    min-width: 2rem;
}

.table-pagination .shinobi-pagination-curpage {
    width: 3rem;
    text-align: center;
}

.table-pagination .field {
    margin-bottom: 0;
}

.table-pagination .label-mobile {
    display: block;
}

.table-pagination .label-mobile {
    display: none;
}

@media screen and (max-width: 768px) {
    .table-pagination .label-desktop {
        display: none;
    }

    .table-pagination .label-mobile {
        display: block;
    }
}

.table-pagination-small .table-pagination .select-record-per-page-container {
    display: none;
}
```

### JS

* mapping.js
* api.js
* util.js
* all.min.js //fontAwesomesIcon library

```markup
<script src="https://naruto.finance/static/js/component/mapping.js"></script>
<script src="https://naruto.finance/static/js/component/api.js"></script>
<script src="https://naruto.finance/static/js/component/util.js"></script>
<script src="https://naruto.finance/static/js/library/all.min.js"></script>
```



## Cách dùng

### Cách khai báo HTML chung

các hàm JS gọi ra để thực thi đều có chung khai báo HTML 

#### Bước 1: Thêm JS, CSS vào trang 

{% tabs %}
{% tab title="CSS" %}
```markup
<style>
    @keyframes spinAround {
        from {
            transform: rotate(0deg);
        }

        to {
            transform: rotate(359deg);
        }
    }

    @keyframes spinAround {
        from {
            transform: rotate(0deg);
        }

        to {
            transform: rotate(359deg);
        }
    }

    .table-pagination {
        margin-top: 0.75rem;
        margin-bottom: 0.75rem;
        padding: 0.75rem;
        display: flex;
        justify-content: flex-end;
    }

    .table-pagination .select-record-per-page-container,
    .table-pagination .select-page-container {
        display: flex;
        padding: 0;
        margin-left: 2rem;
    }

    .table-pagination .select-page-container {
        display: flex;
        padding: 0;
        margin-left: 2rem;
    }

    .table-pagination .table-pagination-row-total,
    .table-pagination .table-pagination-page-total,
    .table-pagination .shinobi-pagination-curpage,
    .table-pagination .shinobi-recordperpage {
        font-weight: 700;
    }

    .table-pagination .table-pagination-row-total,
    .table-pagination .table-pagination-page-total,
    .table-pagination .shinobi-pagination-curpage {
        line-height: 1.75;
    }

    .table-pagination .table-pagination-label {
        margin-left: 0.5rem;
        margin-right: 0.5rem;
        line-height: 1.75;
    }

    .table-pagination .table-pagination-label:last-child {
        margin-right: 0;
    }

    .table-pagination .table-pagination-label:first-child {
        margin-left: 0;
    }

    .table-pagination .shinobi-pagination-prev,
    .table-pagination .shinobi-pagination-next {
        min-width: 2rem;
    }

    .table-pagination .shinobi-pagination-curpage {
        width: 3rem;
        text-align: center;
    }

    .table-pagination .field {
        margin-bottom: 0;
    }

    .table-pagination .label-mobile {
        display: block;
    }

    .table-pagination .label-mobile {
        display: none;
    }

    @media screen and (max-width: 768px) {
        .table-pagination .label-desktop {
            display: none;
        }

        .table-pagination .label-mobile {
            display: block;
        }
    }

    .table-pagination-small .table-pagination .select-record-per-page-container {
        display: none;
    }
</style>
```
{% endtab %}

{% tab title="JS" %}
```

```
{% endtab %}
{% endtabs %}

