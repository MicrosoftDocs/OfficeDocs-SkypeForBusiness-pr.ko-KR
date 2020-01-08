---
title: Lync에서 사용자 사진이 표시되는 방식
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac13f066c24f66640aee1360caf1d341d604474
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40983513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Lync에서 사용자 사진이 표시되는 방식

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-08-25_

**요약:** Lync 클라이언트에 표시 되는 사용자 사진은 사용 중인 Lync 기능 (예: 컨퍼런스 또는 메신저 대화)에 따라 다를 수 있습니다.

Lync 2010에는 다른 Lync 사용자에 게 표시 되는 Lync 프로필에 사진을 포함할 수 있는 기능이 도입 되었습니다. Lync 클라이언트에서 연락처에 대 한 사진을 표시할지 여부를 선택할 수도 있습니다. Lync 2013에서 사용자를 위한 고해상도 사진을 지원 합니다. 이 항목에서는 Lync 클라이언트에서 사용자 사진을 가져오고 표시 하는 방법, 이미지가 저장 되는 위치, 각 이미지 원본에 대 한 제한 사항, 다양 한 Lync services에서 사용자 사진을 사용 하는 방법에 대해 설명 합니다.

<div>

## <a name="planning-considerations"></a>계획 고려 사항

사용자 사진에 대 한 지원 구현 계획을 수립할 때 다음 사항을 고려해 야 합니다.

  - 고화질 사용자 사진 지원 기능을 사용 하려면 사용자의 사서함을 Exchange 2013 및 Lync 사용자 계정에서 Lync 2013 풀에 배치 해야 합니다.

  - 고화질 사용자 사진은 Lync Server 2013 및 Exchange 2013을 모두 사용 하는 환경 에서만 지원 됩니다.

  - Exchange 2010 사서함이 있는 사용자는 항상 AD DS의 **thumbnailPhoto** 특성을 사용자 사진의 원본으로 사용 합니다.

  - AD DS의 **thumbnailPhoto** 특성으로 저장 된 사용자 사진은 외부/페더레이션 대화 상대에 게 표시 되지 않습니다.

  - 사용자 연락처에 대 한 사진이 AD DS에 저장 되어 있는 경우 사용 되는 이미지 파일은 96 × 96 픽셀로 제한 되며 100 KB 파일 크기를 초과할 수 없습니다.

  - Lync Server와 Exchange Server 간의 연결이 끊어지면 AD DS에서 사용자의 저해상도 **thumbnailPhoto** 표시 되며 내부 사용자에만 해당 됩니다.

  - 현재 발표자가 비디오를 사용 하도록 설정 하지 않은 경우 Lync 2013 모임에 고해상도 사용자 사진이 표시 됩니다. 또한 갤러리에서 미리 보기 사진 위로 마우스를 이동 하면 고해상도 사진이 표시 됩니다.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Lync 2010의 사용자 사진

Lync 2010 클라이언트에서 두 가지 옵션 중에서 선택 하 여 프로필에 대 한 사진, **기본 회사 사진** , **웹 주소에서 그림**을 표시할 수 있습니다.

<div>

## <a name="default-corporate-picture"></a>기본 기업 사진

**기본 회사 사진** 옵션을 선택 하면 Lync에서 Active Directory 도메인 서비스 로부터 사용자에 게 표시 되는 사진을 가져옵니다. 사용 되는 이미지는 Active Directory 도메인 서비스의 **thumbnailPhoto** 특성에 대 한 값으로 정의 되는 이미지입니다. 이것은 Exchange에서 Outlook에 이미지를 표시 하는 데 사용 되는 파일입니다.

Active Directory 도메인 서비스의 이미지를 사용할 때 고려할 사항은 다음과 같습니다.

  - 최대 96 픽셀 x 96 픽셀 크기의 이미지만 지원 됩니다. 이미지의 파일 크기는 100 KB로 제한 됩니다.

  - 기본적으로 사용자는 Lync 클라이언트를 통해 직접 **thumbnailPhoto** 특성에 사용 되는 이미지를 변경할 수 있습니다. Active Directory 도메인 서비스를 통해이를 사용 하지 않도록 설정할 수 있습니다.

  - Active Directory 도메인 서비스에 저장 된 이미지는 페더레이션 대화 상대 인 경우에도 조직 외부의 대화 상대에 게 표시 되지 않습니다.

  - 대규모 조직의 경우 많은 사용자를 위해 이미지를 저장 하 고 검색 하면 Active Directory 도메인 서비스 데이터베이스 크기 및 성능에 영향을 줄 수 있습니다.

  - 제한 된 이미지 크기와 파일 크기는 저해상도 이미지만 사용할 수 있다는 의미입니다.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>사용자가 Active Directory 도메인 서비스에서 사용자 사진을 관리 하는 방법

사용자는 Lync 2010 클라이언트를 통해 Active Directory 도메인 서비스 프로필에 사용 되는 이미지를 직접 변경할 수 없습니다. 가능한 경우 다음 옵션 중 하나를 사용 하 여 수행할 수 있습니다.

  - **Sharepoint server**   사용자는 sharepoint 서버의 ' 내 사이트 '에 사진을 업로드 한 다음 [sharepoint의 프로필 동기화를 구성](http://go.microsoft.com/fwlink/p/?linkid=507466) 하 여 Active Directory 도메인 서비스의 **thumbnailPhoto** 특성에 사진을 동기화 할 수 있습니다.

  - **공개적으로 액세스할**   수 있는 url에 저장 된 사진은 사용자가 사용 하려는 이미지에 대해 공개적으로 액세스할 수 있는 url을 지정 하 여 사용자 사진을 구성할 수 있습니다. 이미지는 비밀 번호 없이 공개적으로 액세스할 수 있어야 합니다. 지정 된 웹 주소에 저장 된 이미지는 현재 상태 정보의 연락처 카드 범주를 통해 다른 사용자에 게 전송 됩니다. Lync 클라이언트에서 사용자 사진을 표시 해야 하는 경우 지정 된 웹 주소에서 이미지를 검색 합니다.

  - **Windows PowerShell**   관리자 용 exchange 2010 cmdlet은 exchange 2010 관리 셸에서 [RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet을 실행 하 여 **thumbnailPhoto** 특성을 관리할 수 있습니다. Exchange 2010 cmdlet을 사용 하 여 이미지를 가져올 때 파일 크기는 10kb로 제한 됩니다.

  - **타사 도구**   사용자는 **thumbnailPhoto** 특성에 대 한 사진만 업로드할 수 있습니다.

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>웹 주소의 그림 표시

웹 주소를 사용 하 여 **그림 표시** 옵션을 선택 하면 lync에서 사용자가 입력 한 주소에 이미지를 가져와 lync의 사용자 사진에 맞게 표시 합니다.

웹 주소에서 이미지를 사용할 때 고려할 사항은 다음과 같습니다.

  - 파일 크기 제한은 [새 CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet을 사용 하 여 정의 된 클라이언트 정책의 **Maxphotosizekb** 특성에 의해 결정 됩니다. 기본 크기 제한은 30kb입니다. 최 댓 값은 100 KB입니다. 이미지 해상도에는 제한이 없지만 크기 제한을 초과 하는 이미지 파일을 사용 하려고 하면 Lync 클라이언트에 다운로드 되지 않습니다. 값을 0으로 설정 하 여 Lync에서 모든 사용자 사진을 사용 하지 않도록 할 수 있습니다.

  - 웹 주소의 사용자 사진은 외부 페더레이션된 연락처로 볼 수 있습니다.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>클라이언트 정책 cmdlet을 사용 하 여 사용자 사진 관리

Lync Server 2010에서 클라이언트 정책 설정은 CsClientPolicy cmdlet을 사용 하 여 구성 됩니다. 구성 된 정책 설정은 대역내 프로비저닝을 통해 클라이언트에 게 전송 됩니다. 사용자 사진 환경을 결정 하는 CsClientPolicy cmdlet의 두 가지 매개 변수는 **DisplayPhoto** 및 **Maxphoto sizekb**입니다. **DisplayPhoto** 및 **max광kb** 에 해당 하는 대역내 프로비저닝 매개 변수는 **PhotoUsage**이라고 합니다. **PhotoUsage** 매개 변수에 대 한 값은 **endpointConfiguration** **provisionGroup**를 통해 클라이언트로 전송 됩니다. 자세한 내용은 [클라이언트 정책 및 설정 개요](http://go.microsoft.com/fwlink/?linkid=507470) 를 참조 하세요.

**DisplayPhoto** 매개 변수 값은 사용자 사진 이미지의 원본을 결정 합니다. 지원 되는 값은 다음 표에 나와 있습니다.


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
<td><p>않아야</p></td>
<td><p><strong>내 사진 표시 안 함</strong></p></td>
</tr>
<tr class="even">
<td><p>사진</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>기본 기업 사진</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>웹 주소</p></td>
<td><p><strong>웹 주소의 그림 표시</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Lync 2010 클라이언트에서 사진을 가져오는 방법

Lync 2010에서 사용자 사진은 주소록 서비스를 통해 서버에서 관리 됩니다. Lync 클라이언트는 먼저 메일 그룹 확장 웹 서비스를 통해 제공 되는 서버에서 ABWQ (주소록 웹 쿼리) 서비스를 쿼리하여 사용자 사진을 가져옵니다. 클라이언트는 이미지 파일을 받은 다음 사용자의 캐시에 복사 하 여 표시 해야 할 때마다 이미지를 다운로드 하지 않도록 합니다. 쿼리에서 반환 된 특성 값은 사용자의 캐시 된 주소록 서비스 항목에도 저장 됩니다. 주소록 서비스는 24 시간 마다 캐시 된 모든 이미지를 삭제 하 고, 서버의 캐시에서 새 사용자 이미지를 업데이트 하는 데 최대 24 시간이 걸릴 수 있음을 의미 합니다. [CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet을 사용 하 여 캐시를 강제로 업데이트할 수 있습니다.

현재 상태에 포함 된 사용자 사진에는 Lync 클라이언트에서 사용 가능한 새 이미지가 있는지 여부를 확인 하는 데 사용 하는 연결 된 해시 값이 있습니다. 클라이언트는 현재 상태에 사용 된 이미지 파일에 대 한 변경 내용을 자동으로 알립니다.

<div class=" ">


> [!NOTE]  
> 사진이 GalContacts 데이터베이스에 저장 되지 않기 때문에 사용자 사진을 다운로드 하는 것은 클라이언트 정책 (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">집합-CsClientPolicy</A>)의 <STRONG>addressbookavailability</STRONG> 설정에 따라 달라 집니다.



</div>

ABWQ 서비스에 대 한 쿼리에는 다음 특성이 포함 됩니다.

  - **영상 해시**   이진 사진 데이터의 해시 값으로, 현재 사진이 변경 되었는지 여부를 확인 하는 데 사용 됩니다.

  - **PhotoRelPath**   는 서버에 저장 된 이미지 파일에 대 한 상대 경로를 설정 합니다.

  - **사진 크기**   이미지 파일의 크기 (바이트)입니다.

  - **타임 스탬프**   서버에서 이미지 파일을 마지막으로 다운로드 하 고 클라이언트 캐시로 복사한 날짜와 시간입니다.

그런 다음, 이미지 파일을 검색 한 후 Lync 2010 클라이언트는 쿼리에서 반환 된 특성 값을 클라이언트에서 수신 되는 특성 값과 비교 하 여 해당 쿼리가 서로 다른 지 확인 합니다. 값이 다르면 클라이언트가 HTTP GET 요청을 사용 하 여 로그인 한 사용자의 이미지 파일을 검색 합니다.

또한 클라이언트는 서버에 있는 **사진 해시** 특성 값을 클라이언트의 값과 비교 하기 위해 이미지 파일의 캐시 된 버전을 만든 시간부터 24 시간 마다 서버를 확인 합니다. 값이 다르면 클라이언트는 이미지 파일이 변경 되었음을 인식 합니다. 업데이트 된 이미지 파일을 얻으려면 클라이언트는 ABWQ 서비스를 다시 쿼리하여 클라이언트 캐시의 이미지 파일을 서버의 이미지 파일로 업데이트 하며,이 경우 클라이언트 캐시에서 파일의 **타임 스탬프도** 다시 설정 됩니다.

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

Lync 2013는 사용자 사진에 대 한 고해상도 이미지에 대 한 지원을 도입 했습니다. Lync 2013에는 Exchange 2013의 사용자 사서함에 사용자 사진을 저장 하는 지원도 포함 되어 있어 Lync 2010에 있는 이미지 해상도 및 크기 제한이 제거 됩니다. Lync 2013의 사용자 사진에는 최대 20mb의 파일 크기를 사용 하 여 648 픽셀로 최대 648 픽셀까지 가능 합니다. Lync 2013의 고해상도 사진은 Exchange 2013의 사용자 사서함에 위치 해야 하며 Lync 2013 클라이언트 에서만 지원 됩니다. Exchange와의 이러한 통합은 Oauth, Exchange 및 SharePoint의 2013 버전에 포함 된 새 인증 프레임 워크를 활용 합니다.

Exchange 2013이 배포에 사용 되지 않는 경우 사용자 사진에 대 한 지원은 Lync 2010의 경우와 동일 합니다. 그러나 사용할 사진을 선택 하는 사용자 옵션은 Lync 2013 클라이언트에서 다릅니다. Lync 2013 클라이언트에서 사용자는 **내 사진 숨기기** 또는 **내 사진 표시**중 하나를 선택할 수 있습니다. **웹 사이트의 그림 표시** 옵션은 기본적으로 사용할 수 없지만 클라이언트 정책을 할당 하 여 사용 하도록 설정할 수 있습니다.

<div>

## <a name="hide-my-picture"></a>내 사진 숨기기

사용자 사진에 대 한 설정은 Lync 2013의 **옵션** 대화 상자에 있습니다. **내 사진 숨기기**를 선택 하면 lync 클라이언트에서 사용자 사진이 표시 되지 않지만 대화 상대 카드와 lync 외부에는 여전히 사진이 표시 됩니다.

</div>

<div>

## <a name="show-my-picture"></a>내 사진 표시

**내 사진 표시** 옵션을 선택 하면 lync 클라이언트와 lync 대화의 다른 사용자에 게 사용자 사진이 표시 됩니다. 사용 되는 이미지가 AD DS에 저장 된 이미지입니다.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>웹 사이트의 그림 표시

클라이언트 정책이 사용 하도록 설정 된 후 Lync 2013에서 **웹 사이트에서 그림 표시** 옵션을 사용할 수 있게 됩니다. 클라이언트 버전은 15.0.4535.1002 보다 최신 이어야 하며,이는 [Lync 누적 업데이트: 11 월 2013](http://go.microsoft.com/fwlink/p/?linkid=509908)으로 설치 됩니다. 사용자가 로그 아웃 한 다음 다시 로그인 해야 클라이언트에서 변경 내용을 확인할 수 있습니다.

Lync Server 관리 셸에서 [집합-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy를 실행 하 여 **웹 사이트 설정에서 그림을 표시** 하도록 클라이언트 정책을 설정할 수 있습니다. 다음 예제 cmdlet은 배포의 모든 사용자에 대해 정책을 전역으로 설정 하는 방법을 보여 줍니다.

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


이미지가 사용자의 사서함에 업로드 되 면 Exchange에서 클라이언트 응용 프로그램에 사용할 수 있는 더 낮은 해상도 버전의 이미지를 자동으로 만듭니다. 사용자 사진만 AD DS 에서도 업데이트 됩니다.

<div class=" ">


> [!NOTE]  
> AD DS에서 이미지 파일이 업데이트 되 면 48 x 48 픽셀 이미지가 만들어지고 AD DS의 thumbnailPhoto에 사용 됩니다. 기존 이미지가 바뀝니다. 따라서 AD DS에 96 x 96 이미지를 추가 하면 새 48 x 48 이미지를 사용 하 여 덮어쓰게 됩니다. 이러한 클라이언트는 Lync 2010 클라이언트를 사용 하는 사용자가 AD DS에서 사용자 사진을 얻을 수 있으므로 중요 한 역할을 합니다. 조직에서 Lync 2010 클라이언트를 사용 하는 경우 96 x 96 픽셀 이미지를 가져와 AD DS에서 만든 항목을 바꿀 수 있습니다.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Lync 2013의 사용자 사진 지원

Lync 2013에서 다음 표에 설명 된 대로 사용자 사진에 대 한 세 가지 이미지 해상도가 지원 됩니다. 사용 되는 이미지는 Lync 사용자에 게 할당 된 클라이언트 정책 설정에 따라 결정 됩니다. 자세한 내용은이 항목의 "클라이언트 정책 cmdlet을 사용 하 여 사용자 사진 관리"를 참조 하세요.


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
<td><p>더 높은 해상도의 이미지를 선택 하지 않은 경우 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Outlook Web App 및 Outlook 2013에서 사용 됨</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Lync 2013 데스크톱 클라이언트 및 Lync 2013 웹 앱에서 사용</p></td>
</tr>
</tbody>
</table>


Exchange 2013에서 사서함이 설정 된 사용자는 Outlook Web Access 또는 Lync 2013 클라이언트 옵션을 통해 고해상도 사진을 포함 하 여 다른 이미지를 업로드할 수 있습니다. 사용 하는 이미지에 대해 권장 되는 설정은 다음과 같습니다.

  - **이미지 해상도**   648 x 648 픽셀

  - **색 농도**   24 비트

  - **최대 20mb의 이미지 파일 크기**   

  - **파일 형식**   JPEG

648 x x 648 픽셀에 해당 하는 일반적인 24 비트 JPEG 이미지의 파일 크기는 약 240 KB 이기 때문에 4 사용자 사진 마다 1MB의 저장소 공간이 필요 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

