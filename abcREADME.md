<!DOCTYPE html>
<html>
<head>
  <title>Formulários - Netlify</title>
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/sweetalert2@9.5.3/dist/sweetalert2.min.css" />
  <style>
    body {
      padding-top: 20px;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <form id="formulario" name="formulario-login" method="POST" action="/" data-netlify="true">
          <div class="form-group">
            <label for="exampleInputEmail1">Endereço de email</label>
            <input name="email" type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Seu email">
            <small id="emailHelp" class="form-text text-muted">Nunca vamos compartilhar seu email, com ninguém.</small>
          </div>
          <div class="form-group">
            <label for="exampleInputPassword1">Senha</label>
            <input name="senha" type="password" class="form-control" id="exampleInputPassword1" placeholder="Senha">
          </div>
          <div class="form-group form-check">
            <input name="termos" type="checkbox" class="form-check-input" id="exampleCheck1">
            <label class="form-check-label" for="exampleCheck1">Clique em mim</label>
          </div>
          <button type="submit" class="btn btn-primary">Enviar</button>
        </form>
      </div>
    </div>
  </div>

  <script src="https://code.jquery.com/jquery-3.4.1.min.js" integrity="sha256-CSXorXvZcTkaix6Yvo6HppcZGetbYMGWSFlBw8HfCJo=" crossorigin="anonymous"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
  <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/js/bootstrap.min.js" integrity="sha384-ChfqqxuZUCnJSK3+MXmPNIyE6ZbWh2IMqE241rYiqJxyMiZ6OW/JmZQ5stwEULTy" crossorigin="anonymous"></script>
  <script src="https://cdn.jsdelivr.net/npm/sweetalert2@9.5.3/dist/sweetalert2.all.min.js"></script>
  <script>
    $(document).ready(function ($) {
      const $formulario = $("#formulario");
      
      $formulario.submit(e => {
        e.preventDefault();
        const $action = $formulario.attr('action');
        const $data = $formulario.serialize();
        $.post($action, $data).then(() => {
          Swal.fire({
              icon: 'success',
              title: 'Mensagem Enviada!',
              text: 'Muito obrigado!',
              footer: '<a href="/">Voltar para home</a>'
          });
        });
      });

    });
  </script>
</body>
</html>
