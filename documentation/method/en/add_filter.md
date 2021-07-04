### Your Contribution Needed!
Please edit this page on GitHub :)

$this->add_filter($this->_filter());

private function _filter()
	{
		$output										= null;
		$query										= $this->model->select('id, kode, kecamatan')->order_by('kode')->get('kecamatan')->result_array();
		if($query)
		{
			foreach($query as $key => $val)
			{
				$output								.= '<option value="' . $val['id'] . '"' . ($val['id'] == $this->_id_kec ? ' selected' : '') . '>' . sprintf('%02d', $val['kode']) . '. ' . $val['kecamatan'] . '</option>';
			}
		}
		$output										= '
			<select name="id_kec" class="form-control input-sm bordered" placeholder="' . phrase('filter_berdasar_kecamatan') . '">
				<option value="all">' . phrase('semua_kecamatan') . '</option>
				' . $output . '
			</select>
		';
		return $output;
	}
