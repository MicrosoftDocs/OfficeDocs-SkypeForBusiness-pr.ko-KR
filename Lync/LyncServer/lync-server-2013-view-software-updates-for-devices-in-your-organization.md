---
title: 'Lync Server 2013: 조직의 디바이스에 대 한 소프트웨어 업데이트 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Lync Server 2013의 장치 소프트웨어 업데이트 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Lync Server 2013에서 장치 업데이트 웹 서비스를 사용 하 여 조직의 장치에 대 한 소프트웨어 업데이트를 보고 관리할 수 있습니다. 이러한 업데이트는에서 [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)Microsoft 지원 웹 사이트의 .cab (캐비닛) 파일에서 사용할 수 있습니다. .Cab 파일을 다운로드 한 후에는 **가져오기-CSDeviceUpdate** cmdlet을 실행 하 여 .cab 파일에서 장치 업데이트 규칙을 가져옵니다. **가져오기-csdeviceupdate** cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [가져오기-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 를 참조 하세요.

<div>


> [!TIP]  
> 조직에 새 업데이트를 배포 하기 전에 테스트 장치에서 올바르게 작동 하는지 확인 합니다.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>UC 장치용 소프트웨어 업데이트를 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  의 Microsoft 지원 웹 사이트 [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)에서 Lync Server 2013 컴퓨터의 위치 (예를 들어 C:\\업데이트\\를 다운로드 하는 경우)에 .cab 파일을 다운로드 합니다.

3.  다음 cmdlet 중 하나를 실행 하 여 C\\:\\업데이트 항목 업데이트 .cab 파일에서 장치 업데이트 규칙을 가져옵니다.
    
      - .Cab 파일이 업데이트 될 서비스를 실행 하는 컴퓨터와 같은 컴퓨터에 있는 경우 (서비스: Redmond-websvc-2) 다음 cmdlet을 실행 합니다.
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - .Cab 파일이 업데이트 되는 서비스를 실행 하는 컴퓨터가 아닌 다른 컴퓨터에 있는 경우 (서비스: Redmond-websvc-3) 다음 cmdlet을 실행 합니다.
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

5.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 업데이트**를 클릭 합니다.

6.  **장치 업데이트** 페이지의 목록에서 업데이트를 클릭 하 고 다음 중 하나를 수행 합니다.
    
      - **보류 중인 업데이트를 취소 합니다.** 선택한 업데이트가 조직의 장치에 배포 되지 않도록 하려면 **동작** 메뉴를 클릭 한 다음 **보류 중인 업데이트 취소**를 클릭 합니다.
    
      - **업데이트를 승인 합니다.** 선택한 업데이트를 조직의 장치에 배포할 수 있도록 하려면 **동작** 메뉴를 클릭 한 다음 **승인을**클릭 합니다.
    
      - **업데이트를 복원 합니다.** 이전에 승인 된 업데이트를 조직의 장치에 배포할 수 있도록 하려면 **동작** 메뉴를 클릭 한 다음 **복원을**클릭 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

