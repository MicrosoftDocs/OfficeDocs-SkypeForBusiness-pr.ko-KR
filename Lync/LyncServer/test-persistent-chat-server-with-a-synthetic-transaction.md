---
title: 가상 트랜잭션으로 영구 채팅 서버 테스트
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Test Persistent Chat Server with a synthetic transaction
ms:assetid: 414e43f3-0074-4ecf-a232-398de972cb24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204837(v=OCS.15)
ms:contentKeyID: 48183968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 382e8e664a80b36038d7170d32d243e4e695484e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529765"
---
# <a name="test-persistent-chat-server-with-a-synthetic-transaction"></a><span data-ttu-id="4e94c-102">가상 트랜잭션으로 영구 채팅 서버 테스트</span><span class="sxs-lookup"><span data-stu-id="4e94c-102">Test Persistent Chat Server with a synthetic transaction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e94c-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4e94c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4e94c-104">두 사용자 간에 대화방에서 메시지를 보내고 받을 수 있도록 영구 채팅 서버를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="4e94c-104">To test Persistent Chat Server for sending and receiving messages in a chat room between two users</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] 
        [-OutVerboseVariable <String>] [<CommonParameters>]

<span data-ttu-id="4e94c-105">또는</span><span class="sxs-lookup"><span data-stu-id="4e94c-105">or</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> [-RegistrarPort 
        <Int32>] -SenderCredential <PSCredential> -SenderSipAddress <String> [-TargetFqdn <String>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [<CommonParameters>]

<span data-ttu-id="4e94c-106">또는</span><span class="sxs-lookup"><span data-stu-id="4e94c-106">or</span></span>

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable 
        <String>] [<CommonParameters>]

</div>

<span> </span>

</div>

</div>

</div>

