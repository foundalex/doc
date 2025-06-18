	dev_sel												| ID_AD9361 | 		AD9361 RF Agile Transceiver                               		  | dev_sel
	id_no												| 0	| 				Chip ID 0                                                         | id_no
	reference_clk_rate									| 38400000UL | 		RefClk = 38.4 MHz                                        		  | reference_clk_rate
	two_rx_two_tx_mode_enable							| 1	| 				use 2Rx2Tx mode                                                   | two_rx_two_tx_mode_enable *** adi,2rx-2tx-mode-enable
	one_rx_one_tx_mode_use_rx_num						| 1	| 				N/A when two_rx_two_tx_mode_enable = 1                            | one_rx_one_tx_mode_use_rx_num *** adi,1rx-1tx-mode-use-rx-num
	one_rx_one_tx_mode_use_tx_num						| 1	| 				N/A when two_rx_two_tx_mode_enable = 1                            | one_rx_one_tx_mode_use_tx_num *** adi,1rx-1tx-mode-use-tx-num
	frequency_division_duplex_mode_enable				| 1	| 				use FDD mode                                                      | frequency_division_duplex_mode_enable *** adi,frequency-division-duplex-mode-enable
	frequency_division_duplex_independent_mode_enable	| 1	| 				use independent FDD mode                                          | frequency_division_duplex_independent_mode_enable *** adi,frequency-division-duplex-independent-mode-enable
	tdd_use_dual_synth_mode_enable						| 0	| 				N/A when frequency_division_duplex_mode_enable = 1                | tdd_use_dual_synth_mode_enable *** adi,tdd-use-dual-synth-mode-enable
	tdd_skip_vco_cal_enable								| 0	| 				N/A when frequency_division_duplex_mode_enable = 1                | tdd_skip_vco_cal_enable *** adi,tdd-skip-vco-cal-enable
	tx_fastlock_delay_ns								| 0	| 				TX fastlock delay = 0 ns                                          | tx_fastlock_delay_ns *** adi,tx-fastlock-delay-ns
	rx_fastlock_delay_ns								| 0	| 				RX fastlock delay = 0 ns                                          | rx_fastlock_delay_ns *** adi,rx-fastlock-delay-ns
	rx_fastlock_pincontrol_enable						| 0	| 				RX fastlock pin control disabled                                  | rx_fastlock_pincontrol_enable *** adi,rx-fastlock-pincontrol-enable
	tx_fastlock_pincontrol_enable						| 0	| 				TX fastlock pin control disabled                                  | tx_fastlock_pincontrol_enable *** adi,tx-fastlock-pincontrol-enable
	external_rx_lo_enable								| 0	| 				use internal RX LO                                                | external_rx_lo_enable *** adi,external-rx-lo-enable
	external_tx_lo_enable								| 0	| 				use internal TX LO                                                | external_tx_lo_enable *** adi,external-tx-lo-enable
	dc_offset_tracking_update_event_mask				| 5	| 				apply new tracking word: on gain change, after exiting RX state   | dc_offset_tracking_update_event_mask *** adi,dc-offset-tracking-update-event-mask
	dc_offset_attenuation_high_range					| 6	| 				atten value for DC tracking, RX LO > 4 GHz                        | dc_offset_attenuation_high_range *** adi,dc-offset-attenuation-high-range
	dc_offset_attenuation_low_range						| 5	| 				atten value for DC tracking, RX LO < 4 GHz                        | dc_offset_attenuation_low_range *** adi,dc-offset-attenuation-low-range
	dc_offset_count_high_range							| 0x28 | 			loop gain for DC tracking, RX LO > 4 GHz                          | dc_offset_count_high_range *** adi,dc-offset-count-high-range
	dc_offset_count_low_range							| 0x32 | 			loop gain for DC tracking, RX LO < 4 GHz                          | dc_offset_count_low_range *** adi,dc-offset-count-low-range
	split_gain_table_mode_enable						| 0 | 				use full gain table                                               | split_gain_table_mode_enable *** adi,split-gain-table-mode-enable
	trx_synthesizer_target_fref_overwrite_hz			| MAX_SYNTH_FREF| 	f_ref window 80 MHz                                   			  | trx_synthesizer_target_fref_overwrite_hz *** adi,trx-synthesizer-target-fref-overwrite-hz
	qec_tracking_slow_mode_enable						| 0	| 				don't use improved RX QEC tracking                                | qec_tracking_slow_mode_enable *** adi,qec-tracking-slow-mode-enable	
	------------------------------------------
	ENSM Control
	------------------------------------------
	ensm_enable_pin_pulse_mode_enable					| 0 | 				use level mode on ENABLE and TXNRX pins               		      | ensm_enable_pin_pulse_mode_enable *** adi,ensm-enable-pin-pulse-mode-enable
	ensm_enable_txnrx_control_enable					| 0 | 				use SPI writes for ENSM state, not ENABLE/TXNRX pins  		      | ensm_enable_txnrx_control_enable *** adi,ensm-enable-txnrx-control-enable
	------------------------------------------
	LO Control
	------------------------------------------
	rx_synthesizer_frequency_hz							|2400000000UL|  												  | DEFAULT 		  | rx_synthesizer_frequency_hz *** adi,rx-synthesizer-frequency-hz |
    tx_synthesizer_frequency_hz							|2400000000UL|  												  | DEFAULT 		  | tx_synthesizer_frequency_hz *** adi,tx-synthesizer-frequency-hz |
	------------------------------------------
	Rate & BW Control
	------------------------------------------
	rx_path_clock_frequencies[6]						|{ 983040000, 245760000, 122880000, 61440000, 30720000, 30720000 }| DEFAULT 		  | uint32_t rx_path_clock_frequencies[6] *** adi,rx-path-clock-frequencies
	tx_path_clock_frequencies[6]						|{ 983040000, 122880000, 122880000, 61440000, 30720000, 30720000 }| DEFAULT 		  | uint32_t tx_path_clock_frequencies[6] *** adi,tx-path-clock-frequencies
    rf_rx_bandwidth_hz									|18000000|  													  | DEFAULT 		  | rf_rx_bandwidth_hz *** adi,rf-rx-bandwidth-hz
    rf_tx_bandwidth_hz									|18000000|  													  | DEFAULT 		  | rf_tx_bandwidth_hz *** adi,rf-tx-bandwidth-hz
	------------------------------------------
	RF Port Control
	------------------------------------------
	tx_rf_port_input_select								| 0 | 															  | DEFAULT 		  | rx_rf_port_input_select *** adi,rx-rf-port-input-select
	rx_rf_port_input_select								| 0 | 															  | DEFAULT 		  | tx_rf_port_input_select *** adi,tx-rf-port-input-select
	------------------------------------------
	TX Attenuation Control
	------------------------------------------
	tx_attenuation_mdB									| 10000 | 														  | DEFAULT                                            | tx_attenuation_mdB *** adi,tx-attenuation-mdB
	update_tx_gain_in_alert_enable						| 0	    | 														  | N/A when frequency_division_duplex_mode_enable = 1 | update_tx_gain_in_alert_enable *** adi,update-tx-gain-in-alert-enable
	------------------------------------------
	Reference Clock Control
	------------------------------------------
	xo_disable_use_ext_refclk_enable 					| 1 |              												  | Expect external clock into XTALN            | xo_disable_use_ext_refclk_enable *** adi,xo-disable-use-ext-refclk-enable
    dcxo_coarse_and_fine_tune[2] 						| {3, 5920} |      												  | ~0 ppm DCXO trim (N/A if ext clk)           | dcxo_coarse_and_fine_tune[2] *** adi,dcxo-coarse-and-fine-tune
    clk_output_mode_select 								| CLKOUT_DISABLE | 												  | disable clkout pin (see enum ad9361_clkout) | clk_output_mode_select *** adi,clk-output-mode-select
	