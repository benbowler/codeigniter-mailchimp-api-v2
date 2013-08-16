Codeigniter MailChimp API v2 Wrapper
====================================

Build off the great wrapper by Drew McLellan <drew.mclellan@gmail.com> - Super-simple, minimum abstraction MailChimp API v2 wrapper, in PHP.

Requires curl.

Examples
--------

List lists (lists/list method)

	<?php
	$this->load->library('Mailchimp_library');
	$lists = $this->Mailchimp_library->call('lists/list');
	var_dump($lists):

Subscribe someone to a list

	<?php
	$this->load->library('Mailchimp_library');
	$result = $this->Mailchimp_library->call('lists/subscribe', array(
					'id'                => 'b1234346',
					'email'             => array('email'=>'davy@example.com'),
					'merge_vars'        => array('FNAME'=>'Davy', 'LNAME'=>'Jones'),
					'double_optin'      => false,
					'update_existing'   => true,
					'replace_interests' => false,
					'send_welcome'      => false,
				));
	print_r($result);