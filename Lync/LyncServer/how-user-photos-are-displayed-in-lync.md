---
title: Lync에서 사용자 사진이 표시 되는 방식
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b77d515ebe743b038f3f0099a9702a383e7b797
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505155"
---
# <a name="how-user-photos-are-displayed-in-lync"></a>Lync에서 사용자 사진이 표시 되는 방식

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-08-25_

**요약:** Lync 클라이언트에 표시 되는 사용자 사진은 사용 중인 Lync 기능 (예: 회의 또는 IM 채팅에 있는 경우)에 따라 다를 수 있습니다.

Lync 2010에는 다른 Lync 사용자에 게 표시 되는 Lync 프로필에 사진을 포함할 수 있는 기능이 도입 되었습니다. Lync 클라이언트에서 연락처에 대 한 사진을 표시할지 여부를 선택할 수도 있습니다. Lync 2013에서는 사용자를 위해 고해상도 사진을 지원 합니다. 이 항목에서는 Lync 클라이언트가 사용자 사진, 이미지가 저장 되는 위치, 각 이미지 원본에 대 한 제한 사항, 다양 한 Lync services에서 사용자 사진을 사용 하는 방법에 대해 설명 합니다.

<div>

## <a name="planning-considerations"></a>계획 고려 사항

사용자 사진에 대 한 지원 구현 계획을 수립할 때 다음을 고려해 야 합니다.

  - 고화질 사용자 사진을 지원 하려면 사용자의 사서함이 Exchange 2013에 있고 Lync 사용자 계정이 Lync 2013 풀에 있어야 합니다.

  - 고화질 사용자 사진은 Lync Server 2013 및 Exchange 2013이 모두 사용 되는 환경 에서만 지원 됩니다.

  - Exchange 2010에 사서함이 있는 사용자는 항상 AD DS의 **thumbnailPhoto** 특성을 사용자 사진의 원본으로 사용 합니다.

  - AD DS의 **thumbnailPhoto** 특성으로 저장 된 사용자 사진은 외부/페더레이션 대화 상대에 게 표시 되지 않습니다.

  - 사용자 연락처에 대 한 사진이 AD DS에 저장 된 경우 사용 되는 이미지 파일은 96 × 96 픽셀로 제한 되며, 100 개 이하의 파일 크기는 사용할 수 없습니다.

  - Lync Server와 Exchange Server 간의 연결이 끊어지면 사용자의 낮은 해상도가 AD DS에서 **thumbnailPhoto** , 내부 사용자에만 표시 됩니다.

  - 고해상도 사용자 사진은 현재 발표자가 비디오를 사용할 수 없는 경우 Lync 2013 모임에 표시 됩니다. 또한 갤러리의 축소판 그림 위로 마우스를 이동 하면 고해상도 사진이 표시 됩니다.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010의 사용자 사진

Lync 2010 클라이언트에서는 사용자 프로필에 대 한 사진, **기본 회사 사진** 및 **웹 주소에서 그림**을 표시 하는 두 가지 옵션을 선택할 수 있습니다.

<div>

## <a name="default-corporate-picture"></a>기본 회사 사진

**기본 회사 그림** 옵션을 선택 하면 Lync에서 Active Directory 도메인 서비스 로부터 사용자에 게 표시 되는 사진을 가져옵니다. 사용 되는 이미지는 Active Directory 도메인 서비스의 **thumbnailPhoto** 특성에 대 한 값으로 정의 된 이미지입니다. 이 파일은 Exchange에서 Outlook의 이미지를 표시 하는 데 사용 하는 것과 같은 파일로,

Active Directory 도메인 서비스에서 이미지를 사용할 때 고려해 야 할 사항은 다음과 같습니다.

  - 크기가 최대 96 96 픽셀인 이미지만 지원 됩니다. 이미지의 파일 크기는 100로 제한 됩니다.

  - 기본적으로 사용자는 **thumbnailPhoto** 특성에 사용 되는 이미지를 직접 Lync 클라이언트를 통해 변경할 수 없습니다. Active Directory 도메인 서비스를 통해이를 사용 하지 않도록 설정할 수 있습니다.

  - Active Directory 도메인 서비스에 저장 된 이미지는 페더레이션 연락처 인 경우에도 조직 외부의 대화 상대에 게 표시 되지 않습니다.

  - 대규모 조직에서는 많은 사용자를 위해 이미지를 저장 및 검색 하면 Active Directory 도메인 서비스 데이터베이스 크기 및 성능에 영향을 줄 수 있습니다.

  - 제한 된 이미지 크기와 파일 크기는 저해상도 이미지만 사용할 수 있다는 것을 의미 합니다.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>사용자가 Active Directory 도메인 서비스에서 사용자 사진을 관리 하는 방법

사용자는 Lync 2010 클라이언트를 통해 Active Directory 도메인 서비스 프로필에 사용 되는 이미지를 직접 변경할 수 없습니다. 사용 가능한 경우 다음 옵션 중 하나를 사용 하 여이 작업을 수행할 수 있습니다.

  - **SharePoint Server**     사용자는 SharePoint Server의 ' 내 사이트 '에 사진을 업로드 한 다음 [sharepoint에서 프로필 동기화를 구성](https://go.microsoft.com/fwlink/p/?linkid=507466) 하 여 Active Directory 도메인 서비스의 **thumbnailPhoto** 특성에 사진을 동기화 할 수 있습니다.

  - **공개적으로 액세스할 수 있는 URL**     에 저장 된 사진 사용자는 사용 하려는 이미지에 대해 공개적으로 액세스할 수 있는 URL을 지정 하는 사용자 사진을 구성할 수 있습니다. 이미지는 암호 없이 공개적으로 액세스할 수 있어야 합니다. 지정한 웹 주소에 저장 된 이미지는 현재 상태 정보의 대화 상대 카드 범주를 통해 다른 사용자에 게 전송 됩니다. Lync 클라이언트에서 사용자 사진을 표시 해야 하는 경우에는 지정 된 웹 주소에서 이미지를 검색 합니다.

  - **Windows PowerShell**     용 Exchange 2010 cmdlet 관리자는 **thumbnailPhoto** 특성을 관리 하기 위해 Exchange 2010 관리 셸에서 [import-recipientdataproperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet을 실행할 수 있습니다. Exchange 2010 cmdlet을 사용 하 여 이미지를 가져올 때 파일 크기는 10kb로 제한 됩니다.

  - 타사 **도구**     사용자는 **thumbnailPhoto** 특성에 대해 자신의 사진만 업로드할 수 있습니다.

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>웹 주소의 사진 표시

**웹 주소에서 그림 표시** 옵션을 선택 하면 lync에서 입력 한 주소에 이미지를 가져오고 사용자 사진에 대해 lync에 표시 합니다.

웹 주소에서 이미지를 사용할 때 고려해 야 할 사항은 다음과 같습니다.

  - 파일 크기 제한은 [새-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet을 사용 하 여 정의 되는 클라이언트 정책의 **maxphotosizekb** 특성에 의해 결정 됩니다. 기본 크기 제한은 30kb입니다. 최대값은 100입니다. 이미지 해상도에 대 한 제한은 없지만 크기 제한을 초과 하는 이미지 파일을 사용 하려고 하면 Lync 클라이언트에 다운로드 되지 않습니다. 이 값을 0으로 설정 하 여 모든 사용자 사진이 Lync에서 사용 되지 않도록 설정할 수 있습니다.

  - 웹 주소의 사용자 사진은 외부 페더레이션 대화 상대에 게 표시 될 수 있습니다.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>클라이언트 정책 cmdlet을 사용 하 여 사용자 사진 관리

Lync Server 2010에서는 클라이언트 정책 설정이 CsClientPolicy cmdlet을 사용 하 여 구성 됩니다. 구성 된 정책 설정은 대역내 프로 비전을 통해 클라이언트에 게 전송 됩니다. 사용자 사진 환경을 결정 하는 CsClientPolicy cmdlet의 두 매개 변수는 **DisplayPhoto** 및 **Maxphoto sizekb(** 입니다. **DisplayPhoto** 및 **Maxphotosizekb** 해당 하는 대역내 프로 비전 매개 변수는 **PhotoUsage**로 지정 됩니다. **PhotoUsage** 매개 변수의 값은 **endpointConfiguration** **provisionGroup**를 통해 클라이언트로 전송 됩니다. 자세한 내용은 [클라이언트 정책 및 설정 개요](https://go.microsoft.com/fwlink/?linkid=507470) 를 참조 하세요.

**DisplayPhoto** 매개 변수 값은 사용자의 사진 이미지 원본을 결정 합니다. 다음 표에는 지원 되는 값이 포함 되어 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>DisplayPhoto 매개 변수 값</th>
<th>이미지 원본</th>
<th>Lync 2010 클라이언트 설정</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>없음</p></td>
<td><p><strong>내 사진을 표시하지 않음</strong></p></td>
</tr>
<tr class="even">
<td><p>사진 Fromadonly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>기본 회사 사진</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>웹 주소</p></td>
<td><p><strong>웹 주소의 사진 표시</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 클라이언트에서 사진을 가져오는 방법

Lync 2010에서는 사용자 사진이 주소록 서비스에 의해 서버에서 관리 됩니다. Lync 클라이언트는 먼저 메일 그룹 확장 웹 서비스를 통해 노출 되는 서버에서 ABWQ (주소록 웹 쿼리) 서비스를 쿼리 하 여 사용자 사진을 가져옵니다. 클라이언트는 이미지 파일을 받은 다음 사용자의 캐시에 복사 하 여 표시 해야 할 때마다 이미지를 다운로드 하지 않도록 합니다. 쿼리에서 반환 된 특성 값은 사용자에 대 한 캐시 된 주소록 서비스 항목에도 저장 됩니다. 주소록 서비스는 캐시 된 모든 이미지를 24 시간 마다 삭제 하므로 새 사용자 이미지를 서버의 캐시에서 업데이트 하는 데 최대 24 시간이 걸릴 수 있습니다. [Update-csaddressbook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet을 사용 하 여 캐시를 강제로 업데이트할 수 있습니다.

현재 상태에 포함 된 사용자 사진에는 Lync 클라이언트가 새로운 이미지를 사용할 수 있는지 여부를 확인 하기 위해 사용 하는 연결 된 해시 값도 포함 되어 있습니다. 현재 상태에서 사용 되는 이미지 파일에 대 한 변경 내용이 클라이언트에 자동으로 통지 됩니다.

<div class=" ">


> [!NOTE]  
> 사진이 GalContacts 데이터베이스에 저장 되지 않기 때문에 사용자 사진을 다운로드 하는 것은 클라이언트 정책 (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">설정-CsClientPolicy</A>)의 <STRONG>addressbookavailability</STRONG> 설정에 종속 되지 않습니다.



</div>

ABWQ 서비스에 대 한 쿼리에는 다음과 같은 특성이 포함 됩니다.

  - **사진 해시**     이진 사진 데이터의 해시 값으로, 현재 사진이 변경 되었는지 여부를 확인 하는 데 사용 됩니다.

  - **PhotoRelPath**     서버에 저장 된 이미지 파일의 상대 경로입니다.

  - **사진 크기**     이미지 파일의 크기 (바이트)입니다.

  - **타임 스탬프**     서버에서 이미지 파일을 마지막으로 다운로드 한 날짜와 시간으로, 클라이언트 캐시에 복사 됩니다.

그런 다음 이미지 파일을 검색 한 후 Lync 2010 클라이언트는 쿼리에서 반환 된 특성 값을 클라이언트에서 수신 되는 특성 값과 비교 하 여 해당 쿼리가 서로 다른 지 여부를 확인 합니다. 값이 다르면 클라이언트는 HTTP GET 요청을 사용 하 여 로그인 한 사용자의 이미지 파일을 검색 합니다.

또한 클라이언트는 서버의 **사진 해시** 특성 값을 클라이언트의 값과 비교 하기 위해 이미지 파일의 캐시 된 버전을 만든 시간부터 24 시간 마다 서버를 확인 합니다. 값이 다르면 클라이언트에서 이미지 파일이 변경 되었음을 알 수 있습니다. 업데이트 된 이미지 파일을 가져오기 위해 클라이언트는 ABWQ 서비스를 다시 쿼리하여 클라이언트 캐시의 이미지 파일을 서버의 이미지 파일로 업데이트 하며,이 경우 클라이언트 캐시의 파일에 **타임 스탬프가** 다시 설정 됩니다.

다음은 ABWQ 서비스에 대 한 쿼리에 대 한 응답의 예입니다.
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Lync 2013의 사용자 사진

Lync 2013에서는 사용자 사진에 대 한 고해상도 이미지 지원이 도입 되었습니다. Lync 2013에는 사용자의 2013 사서함에 사용자 사진을 저장 하는 기능도 포함 되어 있으며,이는 Lync 2010에 있는 이미지 해상도 및 크기 제한이 제거 됩니다. Lync 2013의 사용자 사진에는 최대 648 648 픽셀까지 사용할 수 있으며 파일 크기는 최대 20mb입니다. Lync 2013의 고해상도 사진은 Exchange 2013의 사용자 사서함에 위치 해야 하며 Lync 2013 클라이언트 에서만 지원 됩니다. 이 Exchange와의 통합은 Lync, Exchange 및 SharePoint Oauth 라는 2013 버전에 포함 된 새 인증 프레임 워크를 활용 합니다.

Exchange 2013이 배포에 사용 되지 않는 경우 사용자 사진에 대 한 지원은 Lync 2010와 동일 합니다. 그러나 사용할 사진을 선택할 수 있는 사용자 옵션은 Lync 2013 클라이언트에서 서로 다릅니다. Lync 2013 클라이언트에서 사용자는 **내 그림 숨기기** 또는 **그림 표시**를 선택할 수 있습니다. **웹 사이트의 그림 표시** 옵션은 기본적으로 사용할 수 없지만 클라이언트 정책을 할당 하 여 사용 하도록 설정할 수 있습니다.

<div>

## <a name="hide-my-picture"></a>내 사진 숨기기

사용자 사진에 대 한 설정은 Lync 2013의 **옵션** 대화 상자에 있습니다. **그림 숨기기**를 선택 하면 lync 클라이언트에서는 사용자 사진이 표시 되지 않지만 대화 상대 카드와 lync 외부에는 여전히 사진이 표시 됩니다.

</div>

<div>

## <a name="show-my-picture"></a>내 사진 표시

**내 그림 표시** 옵션을 선택 하면 lync 클라이언트 및 lync 대화의 다른 사용자에 게 사용자 사진이 표시 됩니다. 사용 되는 이미지는 AD DS에 저장 된 것입니다.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>웹 사이트에서 그림 표시

클라이언트 정책이 사용 하도록 설정 된 후 **웹 사이트에서 그림 표시** 옵션을 Lync 2013에서 사용할 수 있습니다. 클라이언트 버전은 [Lync 누적 업데이트: 11 월 2013](https://go.microsoft.com/fwlink/p/?linkid=509908)에 설치 된 15.0.4535.1002 보다 최신 이어야 합니다. 사용자가 로그 아웃 한 다음 다시 로그인 하 여 클라이언트의 변경 내용을 확인 해야 할 수 있습니다.

Lync Server 관리 셸에서는 [CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) 정책을 실행 하 여 **웹 사이트 설정에서 그림을 표시** 하도록 클라이언트 정책을 설정할 수 있습니다. 다음 예제 cmdlet은 배포의 모든 사용자에 대해 정책을 전역적으로 설정 하는 방법을 보여 줍니다.

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


이미지가 사용자 사서함에 업로드 되 면 Exchange에서 클라이언트 응용 프로그램에 사용할 수 있는 더 낮은 해상도 버전의 이미지를 자동으로 만듭니다. 사용자 사진만 AD DS 에서도 업데이트 됩니다.

<div class=" ">


> [!NOTE]  
> AD DS에서 이미지 파일이 업데이트 되 면 48 x 48 픽셀 이미지가 생성 되어 AD DS의 thumbnailPhoto에 사용 됩니다. 기존 이미지는 모두 바뀝니다. 따라서 AD DS에 96 x 96 이미지를 추가한 경우 새 48 x 48 이미지를 사용 하 여 덮어씁니다. 이 기능은 클라이언트에서 Lync 2010 클라이언트를 사용 하는 사용자가 AD DS에서 사용자 사진을 가져오기 때문에 중요 합니다. 조직에 Lync 2010 클라이언트가 있는 경우 96 x 96 픽셀 이미지를 가져와서 AD DS에서 만든 것을 바꿀 수 있습니다.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013의 사용자 사진 지원

Lync 2013에서는 다음 표에 설명 된 것 처럼 사용자 사진에 대해 3 가지 이미지 해상도가 지원 됩니다. 사용 되는 이미지는 Lync 사용자에 게 할당 된 클라이언트 정책 설정에 따라 결정 됩니다. 자세한 내용은이 항목의 "사용자 사진에 대 한 클라이언트 정책 cmdlet 관리"를 참조 하세요.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이미지 해상도 (픽셀)</th>
<th>응용 프로그램</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>더 높은 해상도 이미지를 선택 하지 않은 경우에 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Outlook Web App 및 Outlook 2013에서 사용 됨</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Lync 2013 데스크톱 클라이언트 및 Lync 2013 웹 응용 프로그램에서 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


Exchange 2013에서 사서함이 사용 하도록 설정 된 모든 사용자는 Outlook Web Access 또는 Lync 2013 클라이언트 옵션을 통해 고해상도 사진을 비롯 한 다른 이미지를 업로드할 수 있습니다. 사용 되는 이미지에 권장 되는 설정은 다음과 같습니다.

  - **이미지 해상도**     648 x 648 픽셀

  - **색 농도**     24 비트

  - **이미지 파일 크기**     최대 20mb

  - **파일 형식**     JPEG

일반적인 24 비트 JPEG 이미지에는 648 픽셀 x 648 픽셀로 표시 되는 파일 크기는 약 240 KB 이기 때문에 4 사용자 사진 마다 1MB의 저장소 공간이 필요 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

