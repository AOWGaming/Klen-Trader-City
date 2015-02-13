There Are Two Way's Of Doing This 

1- You Can Put It in Mission's File Such As "epoch.chernarus" File(Clint Side)
To Do So Put The Following Line Into "sever_functions.sqf" AT THE BOTTEM

Paste Code AT THE BOTTEM Of "sever_functions.sqf"

[] execVM "buildings\klentrader.sqf"; //Klen Trader

Then Make A File Callled "buildings" in you "SEVERTYPE.MAPTYPE" Such as "epoch.chernarus"

After You Have Done So Put "klentrader.sqf" In the "buildings" Folder

=======================================================================

2- You Can Put It in Sever File Such As "dayz_epoch" File(Sever Side)
To Do So Put The Following Down In You "sever_functions.sqf" AT THE BOTTEM

Paste Code AT THE BOTTEM Of "sever_functions.sqf"

[] execVM "\z\addons\dayz_server\buildings\klentrader.sqf"; //Klen Trader

Then Make A File Callled "buildings" in you "SEVERTYPE_MAPTYPE" Such as "epoch_chernarus"

After You Have Done So Put "klentrader.sqf" In the "buildings" Folder

========================================================================
EXSAMPLE 
========================================================================
server_logUnlockLockEvent = {
	private["_player", "_obj", "_objectID", "_objectUID", "_statusText", "_status"];
	_player = _this select 0;
	_obj = _this select 1;
	_status = _this select 2;
	if (!isNull(_obj)) then {
		_objectID = _obj getVariable["ObjectID", "0"];
		_objectUID = _obj getVariable["ObjectUID", "0"];
		_statusText = "UNLOCKED";
		if (_status) then {
			[_obj, "gear"] call server_updateObject;
			_statusText = "LOCKED";
		};
		diag_log format["SAFE %5: ID:%1 UID:%2 BY %3(%4)", _objectID, _objectUID, (name _player), (getPlayerUID _player), _statusText];
	};
};

[] execVM "\z\addons\dayz_server\buildings\Klentrader.sqf"; //Klen Trader
