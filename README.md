# Football Match Performance & Player Injury Risk Management
Names: Kirenga Ngamije Serge
ID: 29098
# Problem Statement: 
Modern professional and amateur football clubs face challenges in managing player workload, match performance and injury risks. Tight match schedules, poor rotation planning and too much intense sprinting frequently lead to player fatigue and severe muscular injuries. Without a unified database system that helps track player performances and injury tendencies, coaches and medical staff struggle to make proper data backed selection decisions which causes high injury rates and poor match performance.
# Objectives:
The main objective of this project is to track football match stats, compute players' physical fatigue rates and prevent unsafe team selections. Other objectives include to achieve a well structured schema design & data normalization, PL/SQL automation, database security and interactive analytics.
# Data Source
Dataset Name: European Soccer Database / Match & Player Performance Records
Source: Kaggle
Dataset URL: Kaggle European Soccer Database
Data Volume: Over 25,000 match records, 10,000+ player attribute entries, and granular match event metrics.
Licensing & Privacy: Released under Open Educational License. Contains fully anonymized player performance statistics with no private or sensitive personal identifying information.
# Innovation Approach
Option Chosen: Analytics Dashboard (Visual Intelligence & Reporting)
Tool Used: Power BI connected via Oracle ODBC / Power Query integration.
Description: An interactive dashboard that connects directly to the live Oracle database. It displays high-level Key Performance Indicators (KPIs) such as average team sprint distance, fixture congestion severity, player fatigue indexes, and real-time red-flag alerts for players whose injury risk score exceeds established safety thresholds.
# Planned Tables
TEAMS (Team_ID, Team_Name, Stadium, Coach)
PLAYERS (Player_ID, First_Name, Last_Name, Date_Of_Birth, Position, Team_ID)
MATCHES (Match_ID, Home_Team_ID, Away_Team_ID, Match_Date, Home_Score, Away_Score)
PLAYER_MATCH_STATS (Stat_ID, Match_ID, Player_ID, Minutes_Played, Goals, Assists, Yellow_Cards, Red_Cards, Distance_Covered_Km, Sprints_Count)
INJURY_RECORDS (Injury_ID, Player_ID, Injury_Date, Injury_Type, Expected_Recovery_Days, Status)
AUDIT_LOG (Log_ID, Action_Type, Table_Name, Username, Timestamp, Details)
# Planned PL/SQL Features
Procedures:
sp_register_match_stats: Ingests and validates batch match telemetry data.
sp_update_player_workload: Recalculates 30-day cumulative fatigue and high-intensity metrics.
Functions:
fn_calculate_injury_risk_score(p_player_id): Returns a percentage score indicating injury likelihood based on recent workload spikes and recovery time.
Cursors:
Explicit cursor block to scan team rosters before matchday and auto-generate fitness recommendations for technical staff.
Packages:
pkg_football_management: Modular package grouping routines for performance calculations, roster management, and injury monitoring.
Triggers:
trg_prevent_injured_lineup: Before-insert trigger on match lineup tables that raises an exception (RAISE_APPLICATION_ERROR) if a selected player has an active status in INJURY_RECORDS.
trg_audit_player_status: Trigger to log changes in player injury statuses to AUDIT_LOG.
# References (APA)
Abbott, A. (2023). Workload monitoring and injury prevention in professional football. Journal of Sports Analytics, 9(2), 115–128.
Kaggle. (2025). European Soccer Database: Match events, player stats, and attributes. Retrieved from https://www.kaggle.com
Oracle Corporation. (2026). Oracle Database PL/SQL Language Reference, Release 23c. Oracle Documentation.
Reilly, T. (2005). Science and football: evaluation of match data. Journal of Sports Sciences, 23(6), 633–643.
World Bank. (2025). Data governance and educational data sharing frameworks. World Bank Open Data.
