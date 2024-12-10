#!/bin/bash

# Path to your .env file
envFile=".env"

# Check if the .env file exists
if [[ ! -f $envFile ]]; then
    echo "Error: .env file not found in the current directory."
    exit 1
fi

# Load variables from the .env file
while IFS='=' read -r key value; do
    if [[ $key == "SS_DATABASE_CLASS" ]]; then
        databaseClass=$value
    elif [[ $key == "SS_DATABASE_NAME" ]]; then
        databaseName=$value
    elif [[ $key == "SS_DATABASE_SERVER" ]]; then
        databaseServer=$value
    elif [[ $key == "SS_DATABASE_USERNAME" ]]; then
        databaseUsername=$value
    elif [[ $key == "SS_DATABASE_PASSWORD" ]]; then
        databasePassword=$value
    fi
done < <(grep -v '^#' "$envFile")

# Check if all necessary variables are set
if [[ -z $databaseClass || -z $databaseName || -z $databaseServer || -z $databaseUsername || -z $databasePassword ]]; then
    echo "Error: Missing required database information in .env file."
    exit 1
fi

# Construct and output the mysql command
mysql -u $databaseUsername -p$databasePassword -h $databaseServer -A $databaseNames

