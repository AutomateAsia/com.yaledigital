"use strict";

const path			= require('path');
const ZwaveDriver	= require('homey-zwavedriver');

module.exports = new ZwaveDriver( path.basename(__dirname), {
	debug: false,	
	capabilities: {
		'locked': {
			'command_class'				: 'COMMAND_CLASS_DOOR_LOCK',
			'command_get'				: 'DOOR_LOCK_OPERATION_GET',
			'command_set'				: 'DOOR_LOCK_OPERATION_SET',
			'command_set_parser'		: function( value ){
				return {
					'Door Lock Mode': ( value ) ? 'Door Secured' : 'Door Unsecured'
				}
			},
			'command_report'			: 'DOOR_LOCK_OPERATION_REPORT',
			'command_report_parser'		: function( report ){
				return report['Door Lock Mode'] === 'Door Secured';

			}
		}
	},
	settings: {
		'audio_mode': {
			'index': 1,
			'size': 1
		},
		'auto_relock': {
			'index': 2,
			'size': 1
		},
		'relock_time': {
			'index': 3,
			'size': 1
		},
		'max_tries': {
			'index': 4,
			'size': 1
		},
		'lockout_time': {
			'index': 7,
			'size': 1
		},
		'operating_mode': {
			'index': 8,
			'size': 1
		},
		'one_touch_locking': {
			'index': 11,
			'size': 1
		}
	}
})
