Welcome to the demo:

1. Write Markdown text on the left
2. Hit the __Parse__ button or `⌘ + Enter`
3. See the result to on the right

->add_action('toolbar', 'laporan/administration', 'Cetak RKA', 'btn-info ajax', 'fa fa-print', array('kegiatan' => $this->_id_keg, 'method' => 'print'), true)
