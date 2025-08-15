# opac_menu_manager
Plugin untuk management menu opac

Terapkan di Tema OPAC (Edit Satu Kali apa beda dengan edit tambah manual menunya ya hehehhe malah tambah rempong, iya tapi lain kali tambah menu nda edit lagi):

Buka file folder contoh di template nama foldernya default

./template/default/parts/_navbar.php

Cari blok navigasi menu (biasanya <ul class="nav navbar-nav">...</ul>).

Ganti seluruh blok tersebut dengan kode ini:

PHP

<div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav ml-auto">
            
            <?php
            // Awal kode yang ditambahkan
            if (function_exists('render_opac_menu_items')) {
                render_opac_menu_items();
            }
            ?>
            //Akhir kode yang ditambahkan
            <?php
            $menu_member_active = isset($_GET['p']) && $_GET['p'] === 'member' ? 'active' : '';
            if ($is_login) {
            ?>
              <li class="nav-item <?= $menu_member_active; ?>">
              
              . . . lanjut kode lainnya 
              
Simpan file tersebut.

Sekarang, setiap perubahan yang Anda lakukan di OPAC Menu Manager akan langsung terlihat di OPAC tanpa perlu menyentuh kode lagi.
