# ALT:V ServerConfigParser
 C# Klasse zum parsen der server.cfg Datei
 
# Verwendung der Klasse
	## Initialisierung und parsen
		ServerCfgParser parser = new ServerCfgParser("PFAD_ZUR_SERVER.CFG");
		parser.ParseFile();
	
	## Auslesen und Ändern von Werten sowie das speichern der neuen Configdatei
		var players = (short)parser.GetParameter("players");
		//I.e. players = 1024
		players = 20;
		parser.SetParameter<short>("players", players);
		
		//speichern als server.cfg
		parser.SaveServerConfig();
		
		//oder unter anderem Dateinamen
		parser.SaveServerConfig("server_neu.cfg");
		
	## Umwandeln der Serverconfig ins JSON-Format
	var json = parser.ConvertToJson();
	
	//mit ignorierung von bestimmten Werten
	var json = parser.ConvertToJson("password", "token");

