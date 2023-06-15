# Backup Windows Drivers quickly with this Python Script

With this script you can backup your Windows Drivers without any hassle.

Every driver you install is stored in Windows\System32\DriverStore folder. But it backs up EVERY version of the drivers installed.

The script uses DRIVERQUERY comand to generate a csv file with the drivers that are currently in use and matches against the files in DriverStore folder. If there is a match, it backs up this driver.

There are two backup modes: full and strict.
the modes are set changing the backup_mode variable to one of these two values.
Full mode backs up ALL drivers, including duplicated ones. Strict mode backs up only one copy of each driver files (some drivers uses same files for more than one device in Device Manager). All drivers are still backed up in strict mode.

One issue that I can't still figure out is the char encode problem using os.system() function. Special characters like á, é, ô gets messed up when DRIVERQUERY is called within the script. When the same command is run from cmd or powershell it outputs special characters with no problem.

## License

MIT License (MIT). Read [LICENSE](LICENSE) for more information.