---
title: 비즈니스용 Skype 서버에서 고해상도 사진 사용 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에서 고해상도 사진의 사용을 구성 합니다.'
ms.openlocfilehash: d52cdb2d84fedba0dcbec97cbca4074b1ae12a84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188145"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 고해상도 사진 사용 구성
 
**요약:** Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버에서 고해상도 사진의 사용을 구성 합니다.
  
비즈니스용 Skype 서버 사진에는 사용자의 Exchange Server 2016 또는 Exchange Server 2013 사서함에 저장할 수 있으며,이는 최대 648 픽셀의 사진 크기를 648 픽셀로 허용 합니다. 또한 Exchange Server는 필요에 따라 다양 한 제품에서 사용할 수 있도록 이러한 사진의 크기를 자동으로 조정 합니다. 일반적으로 다음과 같은 세 가지 사진 크기와 해상도를 의미 합니다.
  
- 64 픽셀 x 64 픽셀, Active Directory thumbnailPhoto 특성에 사용 되는 크기 Exchange Server에 사진을 업로드 하는 경우 Exchange에서 자동으로 64 픽셀을 해당 사진의 64 픽셀 버전으로 만들고 사용자의 thumbnailPhoto 특성을 업데이트 합니다. 그러나 반대의 경우도 마찬가지입니다. Active Directory에서 thumbnailPhoto 특성을 수동으로 업데이트 하면 사용자의 Exchange 사서함에 있는 사진이 자동으로 업데이트 되지 않습니다.
    
- 96 픽셀 x 96 픽셀, microsoft outlook 2013 웹 앱, Microsoft Outlook 2013, 비즈니스용 Skype Web App 및 비즈니스용 Skype에 사용 됩니다.
    
- Skype for Business 및 비즈니스용 skype Web app for business for 648 픽셀을 통해 648 픽셀을 사용 하세요.
    
> [!NOTE]
> 리소스가 있는 경우 648 x 648 사진을 업로드 하는 것이 좋습니다. 이는 Office 2013 응용 프로그램에서 최대 해상도와 최적의 화질을 제공 합니다. 크기가 648 x 648이 고 깊이가 24 비트인 각 JPEG 사진의 파일 크기는 약 240 kb입니다. 즉, 4 개 사용자 사진 마다 약 1mb의 디스크 공간이 필요 합니다. 
  
Exchange Web Services를 사용 하 여 액세스 되는 고해상도 사진에는 Outlook 2013 웹 앱을 실행 하는 사용자가 업로드할 수 있습니다. 사용자는 자신만의 사진만 업데이트할 수 있습니다. 그러나 관리자는 Exchange 관리 셸 및 다음과 같은 일련의 Windows PowerShell 명령을 사용 하 여 사용자의 사진을 업데이트할 수 있습니다.
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

앞의 예제에서 첫 번째 명령은 `Get-Content` cmdlet을 사용 하 여 파일 C:\Photos\Kenmyer.jpg의 내용을 읽고 해당 데이터를 $photo 이라는 변수에 저장 합니다. 두 번째 명령에서는 Exchange cmdlet `Set-UserPhoto` 을 사용 하 여 사진을 업로드 하 고 해당 사진을: 진구 Myer의 사용자 계정에 첨부 합니다.
  
> [!NOTE]
> 이 예제에서는: 진구 Myer의 Active Directory 표시 이름이 사용자 계정 Id로 사용 됩니다. 사용자의 SMTP 주소 또는 사용자 계정 이름과 같은 다른 식별자를 사용 하 여 사용자 계정을 참조할 수도 있습니다. 자세한 내용은의 Set UserPhoto cmdlet [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) 에 대 한 설명서를 참조 하세요.
  
사진을 업로드 하는 것은: 진구 Myer의 사용자 계정에 해당 사진을 지정 하는 것과 동등 하지 않습니다. 대신 사진을 업로드 하면 해당 사진의 미리 보기가 Outlook Web App 옵션 페이지에 표시 됩니다. 실제로 해당 사진을 사용자 계정에 할당 하려면 사용자가 옵션 페이지에서 **저장** 을 클릭 해야 하거나 관리자가 예제에서 세 번째 명령을 실행 해야 합니다. 세 번째 명령은 저장 매개 변수를 사용 하 여 사진을: 진구 Myer의 사용자 계정에 할당 합니다.
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

새 사진이 사용자 계정에 할당 되었는지 확인 하려면: 진구 Myer에서 비즈니스용 Skype에 로그온 하 여 **옵션**을 선택한 다음 **내 사진을**선택 합니다. 새로 업로드 된 사진은: 진구의 개인 사진으로 표시 되어야 합니다. 또는 관리자가 Internet Explorer를 시작 하 고 다음과 같은 URL로 이동 하 여 사용자의 사진을 확인할 수 있습니다.
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

관리자가 Internet Explorer를 사용 하 여 사진을 볼 수 있지만 사용자가 비즈니스용 Skype에서 자신의 사진을 볼 수 없는 경우 Exchange Web Services 또는 Exchange 자동 검색 서비스에 연결 문제가 있을 수 있습니다.
  
또한이 사진을 비즈니스용 Skype에서 사용할 수 있도록 하기 위해 추가 구성이 필요 하지 않습니다. 대신 사진이 업로드 되 고 `Set-UserPhoto` cmdlet이 실행 된 후 바로 사용할 수 있게 됩니다.
