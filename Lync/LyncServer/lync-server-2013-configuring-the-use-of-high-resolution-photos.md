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
ms.openlocfilehash: ec832d3795fc1b83c6a838b15c04be9f2e48d6d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a>Microsoft Lync Server 2013에서 고해상도 사진 사용 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-05_

Microsoft Lync Server 2010에서는 사용자가 연락처의 사진을 볼 수 있도록 하 고 다른 사용자가 자신의 사진을 사용 하는 기능을 제공 합니다. 일반적으로 이러한 사진은 Active Directory에서 사용자의 thumbnailPhoto 특성의 일부로 저장되었으며, 이로 인해 사진의 크기와 해상도에 상당한 제한이 있었습니다. thumbnailPhoto 특성은 최대 48 x 48픽셀 크기의 사진을 포함할 수 있기 때문입니다.

그러나 Microsoft Lync Server 2013에서는 사진을 사용자의 Microsoft Exchange Server 2013 사서함에 저장할 수 있습니다. 이에 따라 사진 크기를 최대 648 픽셀, 648 픽셀까지 허용 합니다. 이 외에도 Exchange 2013에서는 필요에 따라 다양 한 제품에서 사용할 수 있도록 이러한 사진의 크기를 자동으로 조정 합니다. 일반적으로 이 자동 조정 기능을 통해 세 가지 사진 크기 및 해상도를 사용할 수 있습니다.

  - 48 x 48 픽셀, Active Directory thumbnailPhoto 특성에 사용 되는 크기 2013 Exchange에 사진을 업로드 하는 경우 Exchange에서 해당 사진의 48 픽셀 버전으로 48 픽셀을 자동으로 만들고 사용자의 thumbnailPhoto 특성을 업데이트 합니다. 그러나 reverse는 그렇지 않으며 Active Directory에서 thumbnailPhoto 특성을 수동으로 업데이트 하는 경우 사용자의 Exchange 2013 사서함에 있는 사진이 자동으로 업데이트 되지 않습니다.

  - 96 픽셀 x 96 픽셀 (Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App 및 Lync 2013)에서 사용 하기 위한 것입니다.

  - 648 Lync 2013 및 Microsoft Lync Web App에서 사용할 때 648 픽셀 단위

<div>


> [!NOTE]  
> 리소스가 충분한 경우 모든 Office 2013 응용 프로그램에서 최대의 해상도와 최적의 화질을 제공하는 648x648 사진을 업로드하는 것이 좋습니다. 크기가 648 x 648이고 비트 수준이 24인 각 JPEG 사진의 파일 크기는 약 240KB입니다. 즉, 4명의 사용자 사진마다 약 1MB가 필요합니다.



</div>

Exchange 웹 서비스를 사용 하 여 액세스 하는 고해상도 사진에는 Outlook 2013 Web App을 실행 하는 사용자가 업로드할 수 있습니다. 사용자는 자신의 사진만 업데이트할 수 있습니다. 그러나 관리자는 Exchange 관리 셸 및 다음과 같은 일련의 Windows PowerShell 명령을 사용 하 여 모든 사용자에 대 한 사진을 업데이트할 수 있습니다.

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

위 예제의 첫 번째 명령은 Get-Content cmdlet을 사용 하 여 C:\\사진\\Kenmyer 파일의 내용을 읽고 해당 데이터를 $photo 이라는 변수에 저장 합니다. 두 번째 명령에서는 Exchange cmdlet Ken 사진을 업로드 하 고 해당 사진을 Myer의 사용자 계정에 연결 하는 데 사용 됩니다.

<div>


> [!NOTE]  
> 이 예에서는 사용자 계정 ID로 Ken Myer의 Active Directory 표시 이름이 사용되었습니다. 또한 사용자의 SMTP 주소 또는 사용자 계정 이름 등의 다른 식별자를 사용하여 사용자 계정을 참조할 수도 있습니다. 자세한 내용은에 <A href="https://go.microsoft.com/fwlink/p/?linkid=268536">https://go.microsoft.com/fwlink/p/?LinkId=268536</A> 있는 Set userphoto cmdlet 설명서를 참조 하세요.



</div>

사진을 업로드한다고 해서 해당 사진이 Ken Myer의 사용자 계정에 할당되는 것은 아닙니다. 사진을 업로드하면 단지 Outlook Web App 옵션 페이지에 해당 사진의 미리 보기가 표시됩니다. 실제로 사진을 사용자 계정에 할당하려면 사용자가 옵션 페이지에서 **저장**을 클릭하거나 관리자가 위 예에 있는 세 번째 명령을 실행해야 합니다. 세 번째 명령은 다음과 같이 Save 매개 변수를 사용하여 사진을 Ken Myer의 사용자 계정에 할당합니다.

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

새 사진이 사용자 계정에 할당 되었는지 확인 하기 위해 Ken Myer에서 Lync 2013에 로그온 하 고 **옵션**을 선택한 다음 **내 그림**을 선택할 수 있습니다. 그러면 새로 업로드된 사진이 Ken의 개인 사진으로 표시됩니다. 또한 관리자의 경우 Internet Explorer를 시작하고 다음과 유사한 URL로 이동하여 모든 사용자의 사진을 확인할 수 있습니다.

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

관리자가 Internet Explorer를 사용 하 여 사진을 볼 수 있으 나 사용자가 Lync 2013에서 해당 사진을 볼 수도 없으며,이는 일반적으로 Exchange 웹 서비스와의 연결 문제 또는 Exchange 자동 검색 서비스를 사용 하는 것을 나타냅니다.

Lync 2013에서이 사진을 사용할 수 있도록 하기 위해 추가 구성이 필요 하지는 않습니다. 대신, 사진이 업로드 되 고 UserPhoto cmdlet이 실행 된 후에 즉시 사용할 수 있게 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

