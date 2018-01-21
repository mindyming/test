if [ $# -ne 1 ]
then
 echo " Usage:usr_monitor user_name "
  exit
fi

temp=$1
who -q >> $temp
echo "user on line : $USER "

echo " $USER $LOGNAME " >> $temp

if who | grep -w $1 $temp

then
echo " user $1 is logon "
else
echo " waiting user $1 ... "
fi
