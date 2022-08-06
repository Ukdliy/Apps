function main(Tanggal,Sebagai,Kelas) {


  const sheet_ID = "1zftwU5sNM7wIDn7-MwJTrBLv3b49Rgzcxq-BlO3Z6i8"


  const ss = SpreadsheetApp.openById(sheet_ID)
  const sheet = ss.getSheetByName("Form")

  const START_COLUMN = 1
  const START_ROW = 2

  const body = "Data Masuk" +  "<br><br>" +
               "Tanggal Masuk       : " + Tanggal +  "<br><br>" +
               "Sebagai             : " + Sebagai +  "<br><br>" +
               "Kelas               : " + Kelas +  "<br><br>";

  const target_email = Session.getActiveUser().getEmail()
  const email_Subject = "Data Masuk";
  MailApp.sendEmail(target_email,email_Subject,"",{htmlBody: body})
  
}
