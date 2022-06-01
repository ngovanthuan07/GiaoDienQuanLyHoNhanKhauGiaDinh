# GiaoDienQuanLyHoNhanKhauGiaDinh
# Thư viện hỗ trợ lấy địa chỉ (Yêu cầu sử dụng Bootstrap 4)
- Bước 1: import 2 thẻ javascript vào trong projet
```
    <script src="./js/modal-form.js"></script>
    <script type="module" src="./js/address-form.js"></script>
```
- Bước 2: thêm thẻ thẻ div vào dưới body
```
    <div id = "my-modal"></div>
```
- Bước 3 Trong các thẻ input ta thêm vào attribute
```
    data-toggle="modal"
    data-target="#exampleModal"
    modal-form
```

# Tab menu
- HTML
```
        <!-- add tab -->
        <p style="float:right; margin-right: 5%;">
            <button
              id="btn-add-tab"
              type="button"
              class="btn btn-info"
            >
             +  Thêm 1 nhân khẩu
            </button>
          </p>
        <!-- content -->
        <div class="col-md-12">
            <nav>
                <div class="nav nav-tabs" id="nav-tab" role="tablist">
                  <a class="nav-item nav-link active" id="nav-item-tab-0" data-toggle="tab" href="#tab-0" role="tab" aria-controls="tab-0" aria-selected="true">Trang chu</a>
                </div>
              </nav>
              <div class="tab-content" id="nav-tabContent">
                <div class="tab-pane fade show active" id="tab-0" role="tabpanel" aria-labelledby="nav-home-tab">1</div>
              </div>
        </div>
```
- JS
```

let navTab = document.getElementById('nav-tab')
let navTabContent = document.getElementById('nav-tabContent')
let btnAddTab = document.getElementById('btn-add-tab')
let idTab = 0;

btnAddTab.onclick = handleAddTab

function handleAddTab() {
    idTab++;
    navTab.innerHTML += `
        <a class="nav-item nav-link" id="nav-item-tab-${idTab}" data-toggle="tab" href="#tab-${idTab}" role="tab" aria-controls="tab-${idTab}" aria-selected="false">
            NK${idTab} &ensp; <i class="fa-solid fa-x text-danger" onclick="handleDeleteTab('${idTab}',this)"></i>
        </a>
    `

    navTabContent.innerHTML += `
        <div class="tab-pane fade" id="tab-${idTab}" role="tabpanel" aria-labelledby="nav-contact-tab">
            The Content ${idTab}
        </div>
    `
}

function handleDeleteTab(tabId,_this) {
    const elementTab = document.getElementById(`nav-item-tab-${tabId}`);
    const elementContent = document.getElementById(`tab-${tabId}`);
    elementTab.remove()
    elementContent.remove()
}
```
