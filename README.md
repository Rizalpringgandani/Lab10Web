# Tugas Pemrograman Web 2
# Praktikum 10
## Profile
<body>
    <table border="1">
        <tr>
            <th> Nama</th>
            <th>NIM</th>
            <th>Kelas</th>
        </tr>
        <tr>
            <td>Rizal Pringgandani</td>
            <td>312110151</td>
            <td>TI.21.A2</td>
        </tr>
    </table>
</body>

## Intruction
Melanjutkan praktikum sebelumnya pada repository dengan nama **`Lab9web.`**

## Step by Step pagination


## ubah method admin_index()
```
public function admin_index()
   {
      $title = 'Daftar Artikel';
      $q = $this->request->getVar('q') ?? '';
      $model = new ArtikelModel();
      $data = [
          'title'   => $title,
          'q'       => $q,
          'artikel' => $model->like('judul', $q)->paginate(4, 'bootstrap'), #data dibatasi 4 record perhalaman
          'pager'   => $model->pager,
      ];
      return view('artikel/admin_index', $data);
      }
```


## tambahan pada file admin_index.php yang terletak di directori views\artikel
tuliskan kode di bawah deklarasi table data
```
<?= $pager->only(['q'])->links('bootstrap', 'bootstrap_pagination'); ?>
```

## Step Membuat fitur Pencarian

## tambahan pada file admin_index.php yang terletak di directori views\artikel
tuliskan kode diatas deklarasi table data
```
<form method="get" class="form-search">
<input type="text" name="q" value="<?= $q; ?>" placeholder="Cari data">
<input type="submit" value="Cari" class="btn btn-primary">
</form>
```
## ubah method admin_index()
```
public function admin_index()
   {
      $title = 'Daftar Artikel';
      $q = $this->request->getVar('q') ?? '';
      $model = new ArtikelModel();
      $data = [
          'title'   => $title,
          'q'       => $q,
          'artikel' => $model->like('judul', $q)->paginate(4, 'bootstrap'), #data dibatasi 4 record perhalaman
          'pager'   => $model->pager,
      ];
      return view('artikel/admin_index', $data);
      }
```

- Akses File  dengan url :  http://localhost:8080/user/login 

## Outvut

![Image](img/ss1.png)



## Done
