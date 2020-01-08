---
title: 'Lync Server 2013: 컴퓨터에서 실행 중인 서비스의 상태를 봅니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52f7b1628f9e9fcd99eea84ebda2cbfe934fc7d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a>Lync Server 2013에서 컴퓨터에 실행 중인 서비스의 상태 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

Lync Server 2013 제어판을 사용 하 여 Lync Server 토폴로지의 특정 컴퓨터에서 실행 중인 모든 서비스를 보고 각 서비스의 상태를 확인할 수 있습니다.

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a>컴퓨터에서 실행 중인 서비스의 상태를 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **토폴로지**를 클릭 합니다.

4.  **상태** 페이지에서 필요에 따라 목록을 정렬 하거나 검색 하 여 원하는 컴퓨터를 찾은 다음 컴퓨터 이름을 클릭 합니다.

5.  다음 중 하나를 수행 합니다.
    
      - 컴퓨터에서 실행 중인 서비스의 최신 상태를 보려면 **서비스 상태 가져오기를**클릭 합니다.
    
      - 컴퓨터에서 실행 되는 특정 서비스 목록과 각 서비스의 상태를 확인 하려면 **속성**을 클릭 한 다음 **닫기를** 클릭 하 여 목록으로 돌아갑니다.

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 서비스 상태 보기

Windows PowerShell 및 **Get CsWindowsService** cmdlet을 사용 하 여 서비스 상태를 볼 수도 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-service-status"></a>서비스 상태를 보려면

  - 컴퓨터에서 서비스 상태를 보려면 Lync Server 관리 셸에서 다음과 유사한 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    이 명령은 다음과 같은 정보를 반환 합니다.
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

자세한 내용은 [CsWindowsService 가져오기](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)를 참조 하세요.

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

