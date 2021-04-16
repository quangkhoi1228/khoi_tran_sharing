# Datalist.js

## Datalist.js là gì?

datalist.js là một thư viện dùng để hiển thị dữ liệu dạng list JSON hoặc [dữ liệu dạng findDataList](https://quangkhoi1228.gitbook.io/guide/shinobi-js-core/gioi-thieu-shinobi-js-core#du-lieu-dang-finddatalist) lên giao diện, các dữ liệu này thể hiện trên giao diện theo dạng các phần tử HTML lặp lại 1 cấu trúc giống như 1 list, 1 table hay vòng lặp,...

![V&#xED; d&#x1EE5; v&#x1EC1; c&#xE1;c element HTML d&#x1EA1;ng l&#x1EB7;p &#x111;i l&#x1EB7;p l&#x1EA1;i](../.gitbook/assets/image%20%2837%29.png)

## Cách dùng

### Cách khai báo HTML chung

các hàm JS gọi ra để thực thi đều có chung khai báo HTML 

#### Bước 1: Thêm JS, CSS vào trang 

{% tabs %}
{% tab title="JS" %}
```markup
<script src="https://naruto.finance/static/js/component/mapping.js"></script>
<script src="https://naruto.finance/static/js/component/api.js"></script>
<script src="https://naruto.finance/static/js/component/util.js"></script>
<script src="https://naruto.finance/static/js/library/all.min.js"></script>
<script src="https://naruto.finance/static/js/component/datalist.js"></script>
```
{% endtab %}

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
{% endtabs %}

#### Bước 2: Thêm HTML

{% tabs %}
{% tab title="Cú pháp" %}
```markup
 <parentTagname id="datalistId" snb-datalist-node="datalistId">
    <childTagname snb-datalist-parent="datalistId">
        ... 
    </childTagname>
</parentTagname>
#{{paginationHTML}}
```
{% endtab %}

{% tab title="Ví dụ" %}
```markup
<div id="datalist1" snb-datalist-node="datalist1" class="hero-body">
    <div snb-datalist-parent="datalist1" class="card">
        <div class="card-content">
            <div class="content">
                <p snb-key="id"></p>
                <p snb-key="name"></p>
                <p snb-key="age"></p>
            </div>
        </div>
    </div>
</div>
#{{paginationHTML}}
```
{% endtab %}

{% tab title="paginationHTML" %}
```markup
<div class="table-pagination">
    <div class="columns is-mobile">
        <div class="column select-record-per-page-container">
            <span class="table-pagination-label"> Hiện</span>
            <div class="select is-primary is-small">
                <select class="shinobi-recordperpage"
                    snb-key="recordPerPage">
                    <option value="5">5</option>
                    <option value="10">10</option>
                    <option value="15">15</option>
                </select>
            </div>
            <span class="table-pagination-label"><span
                    class="label-desktop">trong số</span><span
                    class="label-mobile">/</span></span>
            <span class="table-pagination-row-total"
                snb-key="rowTotal">30</span>
        </div>
        <div class="column select-page-container">
            <span class="table-pagination-label">Trang</span>
            <div class="field has-addons">
                <p class="control">
                    <a
                        class="button is-primary is-small shinobi-pagination-prev"><span
                            class="icon"><i
                                class="fa fa-chevron-left"></i></span>
                    </a>
                </p>
                <p class="control">
                    <input
                        class="input is-primary is-small shinobi-pagination-curpage"
                        snb-key="currentpage" value="1" />
                </p>
                <p class="control">
                    <a
                        class="button is-primary is-small shinobi-pagination-next">
                        <span class="icon"><i
                                class="fa fa-chevron-right"></i></span>
                    </a>
                </p>
            </div>
            <span class="table-pagination-label"><span
                    class="label-desktop">trong</span><span
                    class="label-mobile">/</span></span>
            <span class="table-pagination-page-total"
                snb-key="pageTotal" snb-format="true">1</span>
        </div>
    </div>
</div>
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Diễn giải:

datalist HTML bao gồm 3 thành phần:

1. Container HTML cha khai báo:
   1. `id`: id của container
   2. `snb-datalist-node`: id của datalist node
2. Container HTML con **nằm trong** Container cha khai báo
   1. `snb-datalist-parent` bằng với snb-datalist-node của container cha
   2. các nội dung sẽ được lặp đi lặp lại, **cấu trúc nội dung sẽ được quy định theo format của mapping.js**
3. Container chứa đoạn HTML **nằm kế dưới Container cha** trong file HTML chứa nội dung phân trang, nội dung được để trong  tab **paginationHTML**

**\*Khi thực thi JS datalist.js container HTML con sẽ được loop dựa theo số lượng dữ liệu và nằm trong container cha**
{% endhint %}

### Khởi tạo đối tượng datalist

 Để sử dụng các chức năng của datalist.js ta cần phải khởi tạo đối tượng shinobi.datalist bằng cú pháp:

{% tabs %}
{% tab title="Cú pháp" %}
```javascript
var datalistObject = new shinobi.datalist(datalistId)
```
{% endtab %}

{% tab title="Ví dụ" %}
```javascript
var datalistObject = new shinobi.datalist('datalistId');
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Phải có HTML chung rồi với khởi tạo được hàm shinobi.datalist
{% endhint %}



### Render danh sách JSON lên giao diện

 Để render danh sách JSON lên giao diện ta sử dụng hàm  `renderTable`

```javascript
shinobi.render
```





















