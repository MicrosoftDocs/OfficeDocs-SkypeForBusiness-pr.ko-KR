---
title: 'Lync Server 2013: 고해상도 사진 사용 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cb82c047491a43f2a8682d3a6688f67e76af730
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013에서 고해상도 사진 사용 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-05_

Microsoft Lync Server 2010는 사용자가 연락처의 사진을 볼 수 있는 기능을 제공 하 고 다른 사람들에 게 자신의 사진을 제공 합니다. 일반적으로 이러한 사진은 Active Directory에서 사용자의 thumbnailPhoto 특성의 일부로 저장 되었습니다. 사진의 크기와 해상도에 심각한 제한을 적용 한 경우 thumbnailPhoto 특성은 최대 크기인 48 픽셀을 48 픽셀로만 보유할 수 있습니다.

그러나 Microsoft Lync Server 2013에서는 사진을 사용자의 Microsoft Exchange Server 2013 사서함에 저장할 수 있습니다. 이를 통해 최대 648 픽셀의 사진 크기를 648 픽셀로 할 수 있습니다. 이 외에도, Exchange 2013는 필요에 따라 다양 한 제품에서 사용할 수 있도록 이러한 사진의 크기를 자동으로 조정 합니다. 일반적으로 다음과 같은 세 가지 사진 크기와 해상도를 의미 합니다.

  - 48 픽셀 x 48 픽셀, Active Directory thumbnailPhoto 특성에 사용 되는 크기 Exchange 2013에서 사진을 업로드 하는 경우 Exchange에서 자동으로 해당 사진의 48 픽셀 버전으로 48 픽셀을 만들고 사용자의 thumbnailPhoto 특성을 업데이트 합니다. 그러나 반대의 경우는 아니지만, Active Directory에서 thumbnailPhoto 특성을 수동으로 업데이트 하는 경우 사용자의 Exchange 2013 사서함에 있는 사진이 자동으로 업데이트 되지 않습니다.

  - 96 픽셀 x 96 픽셀, microsoft Outlook 2013 웹 앱, Microsoft Outlook 2013, Microsoft Lync Web App, Lync 2013에 사용 됩니다.

  - Lync 2013 및 Microsoft Lync Web App에서 사용할 때 648 픽셀 x 648 픽셀

<div>


> [!NOTE]  
> 리소스가 있는 경우 648x648 사진을 업로드 하는 것이 좋습니다. 이는 Office 2013 응용 프로그램에서 최대 해상도와 최적의 화질을 제공 합니다. 648x648의 크기와 깊이가 24 비트인 각 JPEG 사진에는 약 240 킬로바이트의 파일 크기가 있습니다. 즉, 4 개 사용자 사진 마다 약 1mb의 디스크 공간이 필요 합니다.



</div>

Exchange Web Services를 사용 하 여 액세스 되는 고해상도 사진에는 Outlook 2013 웹 앱을 실행 하는 사용자가 업로드할 수 있습니다. 사용자는 자신만의 사진만 업데이트할 수 있습니다. 그러나 관리자는 Exchange 관리 셸 및 다음과 같은 일련의 Windows PowerShell 명령을 사용 하 여 사용자의 사진을 업데이트할 수 있습니다.

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

앞의 예제에서 첫 번째 명령은 콘텐츠 가져오기 cmdlet을 사용 하 여 C:\\사진\\Kenmyer의 내용을 읽고 $photo 라는 변수에 해당 데이터를 저장 합니다. 두 번째 명령에서 Exchange cmdlet Set UserPhoto는 사진을 업로드 하 고 해당 사진을: 진구 Myer의 사용자 계정에 첨부 하는 데 사용 됩니다.

<div>


> [!NOTE]  
> 이 예제에서는: 진구 Myer의 Active Directory 표시 이름이 사용자 계정 Id로 사용 됩니다. 사용자의 SMTP 주소 또는 사용자 계정 이름과 같은 다른 식별자를 사용 하 여 사용자 계정을 참조할 수도 있습니다. 자세한 내용은의 Set UserPhoto cmdlet <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> 에 대 한 설명서를 참조 하세요.



</div>

사진을 업로드 하는 것은: 진구 Myer의 사용자 계정에 해당 사진을 지정 하는 것과 동등 하지 않습니다. 대신 사진을 업로드 하면 해당 사진의 미리 보기가 Outlook Web App 옵션 페이지에 표시 됩니다. 실제로 해당 사진을 사용자 계정에 할당 하려면 사용자가 옵션 페이지에서 **저장** 을 클릭 해야 하거나 관리자가 예제에서 세 번째 명령을 실행 해야 합니다. 세 번째 명령은 저장 매개 변수를 사용 하 여 사진을: 진구 Myer의 사용자 계정에 할당 합니다.

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

새 사진이 사용자 계정에 할당 되었는지 확인 하려면: 진구 Myer에서 Lync 2013에 로그온 하 여 **옵션**을 선택한 다음 **내 사진을**선택 합니다. 새로 업로드 된 사진은: 진구의 개인 사진으로 표시 되어야 합니다. 또는 관리자가 Internet Explorer를 시작 하 고 다음과 같은 URL로 이동 하 여 사용자의 사진을 확인할 수 있습니다.

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

관리자가 Internet Explorer를 사용 하 여 사진을 볼 수 있지만 사용자가 Lync 2013에서 자신의 사진을 볼 수 없는 경우 일반적으로 Exchange Web Services 또는 Exchange 자동 검색 서비스의 연결 문제를 나타냅니다.

이 사진을 Lync 2013에서 사용할 수 있도록 하기 위해 추가 구성이 필요 하지 않습니다. 대신 사진이 업로드 되 고 Set UserPhoto cmdlet이 실행 된 후 즉시 사용할 수 있게 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

