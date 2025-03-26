class Login{
    static nomeuser=null;
    static pass=null;
    static logado=false;
    static matriculalogado=null;
    static nomelogado=null;
    static acessologado=null;
    static estilocss= null;
    static callback_ok=null;
    static callback_naook=null;

    static endpoint="https://3a34930d-af1c-4704-9082-c8e2b83dacd4-00-wp6x7m84sjrx.riker.replit.dev/"


    static login=(callback_ok,callback_naook)=>{
        //this.endpoint+=`?matricula=${nomeuser}&senha=${pass}`

        //indexando estilos css
        this.callback_ok=()=>{callback_ok()};this.callback_naook=()=>{callback_naook()};

        this.estilocss=".fundologin {display: flex;justify-content: center;align-items: center;width: 100%;height: 100vh;position: fixed;top: 0px;left: 0px;background-color: #00000088;}"+
        ".labellogin{color: #000;font-weight: 700;}"+"#btnlogin, #btncancelar {color: white;background-color: #000;border-color: #000;padding: 5px;border-radius: 10px;font-size: 1.0em;border-width: 2.5px;}"+"#btnlogin:hover, #btncancelar:hover{background-color: white;color: #000;}"+
        "#lgusername, #lgsenha {width: 250px;padding: 5px;background-color: #fff;height: 20px;font-size: 1.1em;border-width: 2.5px;}"+"#corpologin {display: flex;flex-direction: column;gap: 30px;background-color: white;padding: 20px;border-radius: 20px;}"+".botoeslogin {display: flex;justify-content: center;gap:10px;}";


        const styleEstilo=document.createElement("style");
    
        styleEstilo.innerHTML=this.estilocss;
        styleEstilo.setAttribute("id","estilologin")
        document.head.appendChild(styleEstilo)

        //criando blocos html

        const fundologin=document.createElement("div");
        fundologin.setAttribute("id","fundologin")
        fundologin.setAttribute("class","fundologin");
        document.body.prepend(fundologin)

        const corpologin=document.createElement("div");
        corpologin.setAttribute("id","corpologin")
        corpologin.setAttribute("class","corpologin");
        fundologin.append(corpologin)        

        const campologinusername=document.createElement("div");
        campologinusername.setAttribute("id","campologinusername")
        campologinusername.setAttribute("class","campologin");
        corpologin.append(campologinusername)        
        
        const labelloginusername=document.createElement("label");
        labelloginusername.setAttribute("id","labelloginusername")
        labelloginusername.setAttribute("class","labellogin");
        labelloginusername.innerHTML="Nome de Usuário"
        campologinusername.append(labelloginusername)
        
        const inputusername=document.createElement("input");
        inputusername.setAttribute("id","lgusername");
        inputusername.setAttribute("type","text");
        inputusername.setAttribute("name","lgusername");
        campologinusername.append(inputusername)

        const campologinsenha=document.createElement("div");
        campologinsenha.setAttribute("id","campologinsenha")
        campologinsenha.setAttribute("class","campologin");
        corpologin.append(campologinsenha) 

        const labelloginsenha=document.createElement("label");
        labelloginsenha.setAttribute("id","labelloginsenha")
        labelloginsenha.setAttribute("class","labellogin");
        labelloginsenha.innerHTML="Senha"
        campologinsenha.append(labelloginsenha) 

        const inputsenha=document.createElement("input");
        inputsenha.setAttribute("id","lgsenha");
        inputsenha.setAttribute("type","password");
        inputsenha.setAttribute("name","lgsenha");
        campologinsenha.append(inputsenha) 

        const botoeslogin=document.createElement("div");
        botoeslogin.setAttribute("id","botoeslogin")
        botoeslogin.setAttribute("class","botoeslogin");
        corpologin.append(botoeslogin)
        
        const botaologinacessar=document.createElement("button");
        botaologinacessar.setAttribute("id","btnlogin")
        botaologinacessar.innerHTML="acessar"
        botaologinacessar.addEventListener("click",(evt)=>{
           this.verificarlogin()
        })
        botoeslogin.append(botaologinacessar)

        const botaologincancelar=document.createElement("button");
        botaologincancelar.setAttribute("id","btncancelar")
        botaologincancelar.innerHTML="cancelar"
        botaologincancelar.addEventListener("click",(evt)=>{
            this.fechar()
        })
        botoeslogin.append(botaologincancelar)

    }

    //script

    static verificarlogin=()=>{
        const nomeuser= document.getElementById("lgusername").value;
        const pass= document.getElementById("lgsenha").value;

        //verificação de senha

        const endpoint=`https://3a34930d-af1c-4704-9082-c8e2b83dacd4-00-wp6x7m84sjrx.riker.replit.dev/?matricula=${nomeuser}&senha=${pass}`
        fetch(endpoint).then(res=>res.json()).then(res=>{
            if (res) {
                this.logado=true;
                this.matriculalogado=nomeuser;
                this.nomelogado=res.nome;
                this.acessologado=res.acesso;
                this.callback_ok();
                this.fechar();
            }else{
                this.logado=false;
                this.matriculalogado=null;
                this.nomelogado=null;
                this.acessologado=null;
                this.callback_naook();
                //window.alert("login não efetuado")
                
            }
        })
        
    }

    static fechar=()=>{
        const fundologin = document.getElementById("fundologin")
        fundologin.remove()
        const estilologin=document.getElementById("estilologin")
        estilologin.remove()
    }
}

//export {Login};
