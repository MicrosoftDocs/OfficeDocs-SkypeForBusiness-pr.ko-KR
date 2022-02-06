---
title: 비디오에서 고해상도 사진 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '요약: Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 및 비즈니스용 Skype 서버.'
---

# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>비디오에서 고해상도 사진 비즈니스용 Skype 서버
 
**요약:** Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 비즈니스용 Skype 서버.
  
비즈니스용 Skype 서버 사진은 사용자의 Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 또는 Exchange Online 사서함에 저장할 수 있습니다. 이렇게 하면 최대 648 x 648픽셀의 사진 크기를 사용할 수 있습니다. 또한, Exchange Server 다른 제품에서 사용할 수 있는 이러한 사진의 조정을 자동으로 할 수 있습니다. 일반적으로 이 자동 조정 기능을 통해 세 가지 사진 크기 및 해상도를 사용할 수 있습니다.
  
- 64 x 64픽셀( Active Directory thumbnailPhoto 특성에 사용되는 크기) 사진을 업로드하면 Exchange Server Exchange 64픽셀 버전의 해당 사진이 자동으로 64픽셀을 만들고 사용자의 thumbnailPhoto 특성을 업데이트합니다. 그러나 Active Directory에서 thumbnailPhoto 특성을 수동으로 업데이트하면 사용자의 Exchange 사서함에 있는 사진이 자동으로 업데이트되지 않습니다.
    
- 96 x 96픽셀( Web App, Microsoft Outlook 2013, Microsoft Outlook 2013, 비즈니스용 Skype Web App 및 비즈니스용 Skype.
    
- 648 x 648픽셀로, 비즈니스용 Skype 비즈니스용 Skype Web App 비즈니스용 Skype Web App.
    
> [!NOTE]
> 리소스가 있는 경우 648 x 648 사진을 업로드하는 것이 좋습니다. 는 모든 2013 응용 프로그램에서 최대 해상도 및 최적의 Office 제공합니다. 크기가 648 x 648, 깊이가 24비트인 각 JPEG 사진의 파일 크기는 약 240킬로바이트입니다. 즉, 4명의 사용자 사진마다 약 1MB가 필요합니다. 
  
Exchange 웹 서비스를 사용하여 액세스하는 고해상도 사진은 Outlook 2013 Web App을 실행하는 사용자가 업로드할 수 있습니다. 사용자는 자신의 사진만 업데이트할 수 있습니다. 그러나 관리자는 Exchange 관리 셸 및 다음과 같은 일련의 Windows PowerShell 명령을 사용하여 모든 사용자의 사진을 업데이트할 수 있습니다.
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

위의 예제의 `Get-Content` 첫 번째 명령은 cmdlet을 사용하여 파일 이름의 내용을 읽고 C:\Photos\Kenmyer.jpg 변수에 해당 데이터를 $photo. 두 번째 명령에서는 Exchange cmdlet `Set-UserPhoto` 을 사용하여 사진을 업로드하고 사진을 Ken Myer의 사용자 계정에 첨부합니다.
  
> [!NOTE]
> 이 예에서는 사용자 계정 ID로 Ken Myer의 Active Directory 표시 이름이 사용되었습니다. 또한 사용자의 SMTP 주소 또는 사용자 계정 이름 등의 다른 식별자를 사용하여 사용자 계정을 참조할 수도 있습니다. 자세한 내용은 Set-UserPhoto cmdlet [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) 에 대한 설명서를 참조하십시오.
  
사진을 업로드한다고 해서 해당 사진이 Ken Myer의 사용자 계정에 할당되는 것은 아닙니다. 사진을 업로드하면 단지 Outlook Web App 옵션 페이지에 해당 사진의 미리 보기가 표시됩니다. 실제로 사진을 사용자 계정에 할당하려면 사용자가 옵션 페이지에서 **저장** 을 클릭하거나 관리자가 위 예에 있는 세 번째 명령을 실행해야 합니다. 세 번째 명령은 다음과 같이 Save 매개 변수를 사용하여 사진을 Ken Myer의 사용자 계정에 할당합니다.
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

새 사진이 사용자 계정에 할당되어 있는지 확인하려면 Ken Myer가 사용자 계정에 로그온하여 비즈니스용 Skype **옵션을** 선택한 다음 내 사진을 **선택할 수 있습니다**. 그러면 새로 업로드된 사진이 Ken의 개인 사진으로 표시됩니다. 또한 관리자의 경우 Internet Explorer를 시작하고 다음과 유사한 URL로 이동하여 모든 사용자의 사진을 확인할 수 있습니다.
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

관리자가 Internet Explorer 사용하여 사진을 볼 수 있지만 사용자가 비즈니스용 Skype 웹 서비스 또는 Exchange 자동 검색 서비스에 연결 문제가 Exchange 수 있습니다.
  
또한 이 사진을 다른 사진에서 사용할 수 있도록 설정하기 위해 추가 구성이 비즈니스용 Skype. 대신 사진이 `Set-UserPhoto` 업로드되고 cmdlet이 실행된 후 즉시 사용할 수 있습니다.