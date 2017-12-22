Long War Toolbox
par Long War Studios

Ce mod pour XCOM�2 vient ajouter diff�rentes options de jeu � s�lectionner dans le menu pendant la campagne, ainsi que quelques am�liorations notables.

INSTRUCTIONS D'INSTALLATION 
Steam Workshop�: abonnez-vous au mod sur le Workshop de Long War Studios.

Manuelle/Nexus�: ouvrez l'archive et copiez le r�pertoire LW_Toolbox ainsi que son contenu dans votre version du dossier C:\Program Files (x86)\Steam\steamapps\common\XCOM 2\XComGame\Mods.

Pour jouer�:
Cochez le mod LW_Toolbox dans le Launcher. 

Ce mod modifie automatiquement certains �l�ments, et notamment plusieurs options de l'interface de s�lection de l'escouade. En voici la liste�:

RENDRE ARMES DISPO.�: retire les armes principales de tous les soldats non s�lectionn�s pour la mission.

VIDER ESCOUADE�: retire tous les soldats de l'escouade.

REMPLIR ESCOUADE AUTO.�: remplit automatiquement tous les emplacements vides de l'escouade avec le soldat le plus haut grad� disponible.

L'interface de la liste des soldats a �galement �t� retravaill�e pour lui permettre d'afficher leurs statistiques.

Toutes les autres options peuvent �tre s�lectionn�es via l'onglet Toolbox, dans le menu Options (accessible en appuyant sur la touche �chap). Une fois votre campagne lanc�e, appuyez sur la touche �chap, s�lectionnez MODIFIER LES OPTIONS, puis LW TOOLBOX. REMARQUE�: ces options ne sont pr�sentes que lors des campagnes.

Les options sont�:

ROTATION CAM�RA (DEGR�S)�: permet de contr�ler le degr� de rotation de la cam�ra via les boutons de rotation et toutes touches associ�es.

TAILLE ESCOUADE PAR D�FAUT�: permet de d�finir le nombre maximum de soldats inclus dans l'escouade. Les bonus de l'institut de gu�rilla, une fois termin�s, sont ajout�s � ce chiffre. L'interface et le code de d�ploiement en mission sont d�sormais compatibles avec des escouades pouvant inclure jusqu'� douze soldats. REMARQUE�: le mod n'a pas d'impact sur les escouades de plus grande taille s�lectionn�es par le joueur.

ROULETTE D�G�TS�: les d�g�ts des armes d'XCOM et des extraterrestres varient d'un m�me pourcentage par rapport � leurs d�g�ts de base. Si cette option est d�sactiv�e, le jeu utilisera les m�caniques de base. S�lectionnez "25%" pour que les d�g�ts inflig�s varient de +/-25% par rapport aux d�g�ts de base de l'arme. Cette option �crasera les param�tres d'armes sp�cifi�s dans le fichier INI.

CR�ATION AL�ATOIRE�: Les statistiques initiales des soldats sont d�finies de fa�on al�atoire, selon une certaine base. Ces modifications sont � effet imm�diat, m�me en cours de mission. Si cette option n'est pas s�lectionn�e, les valeurs seront celles par d�faut. Ces statistiques al�atoires sont gard�es en m�moire, et rien n'interdit d'en profiter en d�sactivant et r�activant plusieurs fois cette option. Elle peut �tre utilis�e � tout moment � bord du Talion, ou lors du premier tour d'une mission tactique � condition que personne n'ait �t� bless�. (Il est aussi � noter que modifier les statistiques d'un soldat en cours de mission peut r�sulter dans la mort de celui-ci s'il est bless� et que la modification entra�ne une r�duction des PV.)

POTENTIEL CACHɠ: les statistiques des soldats augmentent de fa�on al�atoire lorsqu'ils gagnent un niveau. Remarque�: les soldats "Easter Egg" sp�ciaux ne sont pas concern�s par cette modification.

BROUILLARD ROUGE�: si cette option est activ�e, les blessures ont un impact sur les statistiques d'attaque, de mobilit�, de piratage et de volont�. Il est possible de choisir qui est affect� par le BROUILLARD ROUGE (XCOM, extraterrestres, les deux ou personne). Quelques extraterrestres, d�finis dans le fichier 'LW_Toolbox.ini', y sont insensibles car ils deviendraient de fait incapables d'agir.

P�NALIT�S DE BROUILLARD ROUGE LIN�AIRES (ET NON QUADRATIQUES)�: par d�faut, les p�nalit�s inflig�es par le brouillard rouge sont limit�es en cas de blessure l�g�re, et importantes en cas de blessure grave. Si l'application est LIN�AIRE, l'effet sera moins prononc�, et une blessure l�g�re � mod�r�e entra�nera une plus grande p�nalit� qu'avec la formule quadratique.

R�SOLUTION AUTOMATIQUE DES COMBATS�: affiche un bouton dans l'interface de s�lection de l'escouade permettant de r�soudre automatiquement un combat tactique avec l'escouade s�lectionn�e, plut�t que de partir en mission.

---------------------------------------------
-----------------CR�DITS---------------------
---------------------------------------------

Responsable technique�: Rachel "Amineri" Norman
Programmation�: Jonathan "tracktwo" Emmett
Responsable conception�: John Lumpkin

---------------------------------------------
----------------AUTORISATIONS------------------
---------------------------------------------

Les cr�ateurs de mods sont libres d'int�grer tout type de code ou de donn�es extrait de ce mod dans le leur, � condition de citer Long War Studios lors de la diffusion du mod.

---------------------------------------------
---------------COMPATIBILIT�-----------------
---------------------------------------------

Les classes remplac�es par ce mod (g�n�ralement non compatible avec les autres mods rempla�ant les m�mes classes)�:
- XComTacticalInput
- UIOptionsPCScreen
- UISquadSelect
- UIAfterAction
- X2TacticalGameRuleset
- UIPersonnel_SquadSelect
- UIPersonnel_SoldierListItem
- UIRecruitmentListItem

Remarques�:
- XComTacticalInput
Permet d'impl�menter des angles de rotation de cam�ra pouvant �tre s�lectionn�s.

- UIOptionsPCScreen
Permet d'impl�menter des options de configuration de mod dans le jeu. 
D'autres mods peuvent utiliser cette interface en cr�ant une extension de classe XComGameState_LWModOptions et en invoquant CreateModSettingsState pour l'ajouter � CampaignSettings.

- UISquadSelect
- UIAfterAction
Permet d'impl�menter une interface pour les escouades de grande taille.
Ajout des accroches suivantes pour permettre aux autres mods d'effectuer des modifications en cas de besoin.
	-- TriggerEvent('OnValidateDeployableSoldiers', DeployableSoldiersTuple, self); // permet aux mods de retirer les soldats ne pouvant pas �tre d�ploy�s pour la mission actuelle
	-- TriggerEvent('PostSquadSelectInit', XComHQ, self);	// permet aux mods de faire des r�glages apr�s l'initialisation du choix de l'escouade
	-- TriggerEvent('OnUpdateSquadSelectSoldiers', XComHQ, XComHQ, NewGameState)  // permet aux mods de retirer ou d'ajouter des soldats au lancement de SquadSelect
	-- TriggerEvent('OnUpdateSquadSelect_ListItem', self, self)   // li� � UISquadSelect_ListItem_LW.Update, permet aux mods d'ajouter des �l�ments aux entr�es de liste individuelles

- X2TacticalGameRuleset
Permet d'�largir une zone d�ployable pour les unit�s au-del� de la grille de base de 3 cases sur 3.

- UIPersonnel_SquadSelect
- UIPersonnel_SoldierListItem
- UIRecruitmentListItem
Permet d'impl�menter l'affichage des statistiques du soldat lors de la consultation et du recrutement des soldats.
Ajout des accroches suivantes pour permettre aux autres mods d'effectuer des modifications en cas de besoin.
	-- TriggerEvent('OnSoldierListItemUpdate_Start', self, self);  // li� � UIPersonnel_SoldierListItem_LW.Update, permet de mettre � jour des �l�ments de d�cor
	-- TriggerEvent('OnSoldierListItemUpdate_End', self, self);  // li� � UIPersonnel_SoldierListItem_LW.Update, permet d'ajouter des �l�ments d'interface par-dessus des �l�ments d�j� existants
	-- TriggerEvent('OnSoldierListItemUpdate_Focussed', self, self);  // li� � UIPersonnel_SoldierListItem_LW.UpdateItemsForFocus, permet de modifier des �l�ments quel que soit l'�tat de la liste
	-- TriggerEvent('OnSoldierListItem_GetPersonnelStatus', self, self); // li� � UIPersonnel_SoldierListItem_LW.GetPersonnelStatusSeparateWrapper, permet d'�craser le statut du personnel
	-- TriggerEvent('OnRecruitmentListItemInit', self, self);   // li� � UIRecruitmentListItem_LW.InitRecruitItem, permet de modifier des �l�ments suppl�mentaires
	-- TriggerEvent('OnRecruitmentListItemUpdateFocus', self, self);  // li� � UIRecruitmentListItem_LW.UpdateItemsForFocus, permet de mettre � jour des �l�ments mis en �vidence
	-- TriggerEvent('OnSoldierListItemUpdateDisabled', UnitItem, self); // li� � UIPersonnel_SquadSelect.UpdateList, permet d'�craser le statut D�sactiv� d'un �l�ment de liste 

Ce mod apporte des modifications aux templates 'Reward_Soldier', 'Reward_Rookie' et 'Reward_CouncilSoldier' de X2StrategyElement_DefaultRewards.
Le fichier d�l�gu� GenerateRewardFn est �cras� dans ces trois cas, et ne sera donc pas compatible avec un autre mod proc�dant � des modifications similaires.
Les fonctions de remplacement viennent ajouter les accroches suivantes, utilisables aussi bien par Toolbox que par d'autres mods :
	-- TriggerEvent( 'SoldierCreatedEvent', NewUnitState, NewUnitState, NewGameState );  // permet d'intercepter les soldats r�cemment cr��s de fa�on � pouvoir les modifier (� l'exception des premiers soldats cr��s au d�marrage de la campagne)
	-- TriggerEvent( 'RankUpEvent', NewUnitState, NewUnitState, NewGameState );   // permet d'intercepter chaque changement de niveau de soldat � la g�n�ration des soldats bonus. � utiliser avec 'PromotionEvent' et 'PsiTrainingCompleted' pour faire en sorte de ne rater aucune occurrence.

---------------------------------------------
------------ REMARQUES POUR LES CR�ATEURS DE MODS --------------
---------------------------------------------

Il est tout � fait possible pour d'autres mods de profiter de la prise de contr�le d'UIOptionsPCScreen par LW Toolbox pour d�finir leurs propres options de jeu � configurer. Chaque mod enregistr� appara�tra dans un nouvel onglet du menu Options. Il s'agit d'une liste � faire d�filer, si plusieurs mods choisissent de configurer leurs options ainsi.

Marche � suivre pour connecter votre mod � LW Toolbox�:

1) Copiez le fichier de classe XComGameState_LWModOptions.uc dans votre mod, dans un dossier distinct, sous /Src/LW_XCGS_ModOptions/Classes/.
2) Ajoutez la ligne de config '+ModEditPackages=LW_XCGS_ModOptions' (de fa�on � correspondre au nouveau dossier dans 'Src') au fichier XComEngine.ini, section [UnrealEd.EditorEngine].
3) Cr�ez une extension de XComGameState_LWModOptions pour int�grer les options de votre mod, en prenant pour exemple XComGameState_LWToolboxOptions.
4) Dans l'extension X2DownloadableContentInfo, ajoutez des liens vers CreateModSettingsState, en prenant pour exemple X2DownloadableContentInfo_LWToolbox.
5) Si le mod LW Toolbox est pr�sent, il trouvera le gamestate ModOptions et remplira automatiquement les options du mod.

Remarques sur l'int�gration de l'extension XComGameState_LWModOptions�:
Le nouveau dossier 'Src' (LW_XCGS_ModOptions) entra�nera la compilation d'un deuxi�me fichier LW_XCGS_ModOptions.u dans le r�pertoire de script de votre mod. Cette action est normale�: elle permet aux composants et au code de ModOptions de fonctionner en l'absence de LW Toolbox. Vous pouvez installer un mod int�grant l'interface AVANT LW Toolbox, et les options fonctionneront une fois Toolbox install�.

-- InitComponent()�:
 Permet d'effectuer une initialisation. Attention, ne peut se produire qu'� la cr�ation du gamestate, et aucune mise � jour n'est possible via code ou autre.

 -- GetTabText()�: 
Fournit le texte � afficher dans UIOptionsPCScreen. La localisation est vivement conseill�e.

-- InitModOptions()�: 
Utilis� � la cr�ation ou � l'initialisation d'UIOptionsPCScreen. Permet de mettre en cache les param�tres actuels ou toute autre chose devant se produire � ce moment pr�cis.

-- SetModOptionsEnabled()�: 
Interface principale entre ModOptions et UIOptionsPCScreen. Fait passer une s�rie d'UIMechaItem � remplir par ModOptions, puis � afficher par UIOptionsPCScreen.

-- HasAnyValueChanged()�: 
Envoie une requ�te � ModOptions pour v�rifier si des modifications sont survenues. Permet d'afficher un avertissement si l'utilisateur quitte UIOptionsPCScreen sans avoir sauvegard� ses modifications.

-- ApplyModSettings()�: 
Appel� lorsque l'utilisateur s�lectionne "Sauvegarder et quitter". Demande � ModOptions d'appliquer toute option choisie par l'utilisateur et pr�alablement s�lectionn�e.

-- RestorePreviousModSettings()�: 
Appel� lorsque l'utilisateur quitte les options sans sauvegarder. ModOptions reprend les options telles qu'elles �taient lorsque l'utilisateur a ouvert UIOptionsPCScreen.

-- CanResetModSettings()�: 
Demande si le mod d�finit un param�tre par d�faut. Permet de placer (ou non) le bouton "Reset Mod Options" ("R�initialiser options du mod"). "Faux" par d�faut, donc sans action de votre part, l'option "R�initialiser" n'appara�tra pas dans votre menu.

-- ResetModSettings()�: 
Rappel du bouton "Reset Mod Options" ("R�initialiser options du mod") permettant de rendre ses valeurs par d�faut au mod s�lectionn�. N'est pas con�u pour sauvegarder les options. Pour sauvegarder, l'utilisateur doit s�lectionner "Sauvegarder et quitter" en sortant. Ne peut �tre appel� que si CanResetModSettings() a �t� modifi� en "Vrai".

--------------------------------------------------

FACULTATIF�:

Toolbox utilise une structure de donn�es LW_Tuple g�n�rique pour faire transiter les donn�es via X2EventManager. Si votre mod a besoin de 'RegisterForEvent' pour l'un de ces 'EventIDs', vous devrez inclure le paquet LW_Tuple�:

1) Copiez le fichier de classe LWTuple.uc dans votre mod, dans un dossier distinct, sous /Src/LW_Tuple/Classes/.
2) Ajoutez la ligne de config '+ModEditPackages=LW_Tuple' (de fa�on � correspondre au nouveau dossier dans 'Src') au fichier XComEngine.ini, section [UnrealEd.EditorEngine].
3) Utilisez la classe LWTuple dans votre code.
