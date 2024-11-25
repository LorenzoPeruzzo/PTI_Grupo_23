# **SaudeLogin**

import '/backend/backend.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:cloud_firestore/cloud_firestore.dart';
import 'package:collection/collection.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_login_model.dart';
export 'saude_login_model.dart';

class SaudeLoginWidget extends StatefulWidget {
  const SaudeLoginWidget({super.key});

  @override
  State<SaudeLoginWidget> createState() => _SaudeLoginWidgetState();
}

class _SaudeLoginWidgetState extends State<SaudeLoginWidget> {
  late SaudeLoginModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeLoginModel());

    _model.emailLoginTextController ??= TextEditingController();
    _model.emailLoginFocusNode ??= FocusNode();

    _model.senhaLoginTextController ??= TextEditingController();
    _model.senhaLoginFocusNode ??= FocusNode();
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Container(
          width: 467,
          height: 962,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
              stops: [0, 1],
              begin: AlignmentDirectional(0, -1),
              end: AlignmentDirectional(0, 1),
            ),
            borderRadius: BorderRadius.only(
              bottomLeft: Radius.circular(32),
              bottomRight: Radius.circular(32),
              topLeft: Radius.circular(32),
              topRight: Radius.circular(32),
            ),
          ),
          child: Column(
            mainAxisSize: MainAxisSize.max,
            children: [
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(7, 64, 0, 0),
                child: ClipRRect(
                  borderRadius: BorderRadius.only(
                    bottomLeft: Radius.circular(0),
                    bottomRight: Radius.circular(0),
                    topLeft: Radius.circular(0),
                    topRight: Radius.circular(0),
                  ),
                  child: Image.asset(
                    'assets/images/Logo+Saude.png',
                    width: 283,
                    height: 282,
                    fit: BoxFit.contain,
                  ),
                ),
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(40, 0, 0, 0),
                      child: Icon(
                        Icons.add,
                        color: Colors.white,
                        size: 74,
                      ),
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 2, 0, 0),
                    child: Text(
                      'SAÚDE',
                      textAlign: TextAlign.center,
                      style:
                          FlutterFlowTheme.of(context).headlineMedium.override(
                                fontFamily: 'Inter Tight',
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                fontSize: 66,
                                letterSpacing: 2,
                                fontWeight: FontWeight.bold,
                              ),
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 16, 0, 0),
                child: Container(
                  width: 356,
                  height: 18,
                  decoration: BoxDecoration(
                    color: Color(0xFF153A71),
                    borderRadius: BorderRadius.only(
                      bottomLeft: Radius.circular(0),
                      bottomRight: Radius.circular(0),
                      topLeft: Radius.circular(11),
                      topRight: Radius.circular(11),
                    ),
                  ),
                  child: Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(4, 1, 0, 0),
                    child: Text(
                      'LOGIN',
                      style: FlutterFlowTheme.of(context).bodyMedium.override(
                            fontFamily: 'Rubik',
                            color: FlutterFlowTheme.of(context)
                                .secondaryBackground,
                            fontSize: 14,
                            letterSpacing: 0.5,
                            fontWeight: FontWeight.w600,
                          ),
                    ),
                  ),
                ),
              ),
              Container(
                width: 353,
                child: TextFormField(
                  controller: _model.emailLoginTextController,
                  focusNode: _model.emailLoginFocusNode,
                  autofocus: false,
                  obscureText: false,
                  decoration: InputDecoration(
                    isDense: true,
                    labelStyle:
                        FlutterFlowTheme.of(context).labelMedium.override(
                              fontFamily: 'Inter',
                              letterSpacing: 0.0,
                            ),
                    hintStyle:
                        FlutterFlowTheme.of(context).labelMedium.override(
                              fontFamily: 'Inter',
                              letterSpacing: 0.0,
                            ),
                    enabledBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: Color(0x00000000),
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    focusedBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: Color(0x00000000),
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    errorBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: FlutterFlowTheme.of(context).error,
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    focusedErrorBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: FlutterFlowTheme.of(context).error,
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    filled: true,
                    fillColor: FlutterFlowTheme.of(context).secondaryBackground,
                  ),
                  style: FlutterFlowTheme.of(context).bodyMedium.override(
                        fontFamily: 'Inter',
                        letterSpacing: 0.0,
                      ),
                  keyboardType: TextInputType.emailAddress,
                  cursorColor: FlutterFlowTheme.of(context).primaryText,
                  validator: _model.emailLoginTextControllerValidator
                      .asValidator(context),
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 16, 0, 0),
                child: Container(
                  width: 356,
                  height: 18,
                  decoration: BoxDecoration(
                    color: Color(0xFF153A71),
                    borderRadius: BorderRadius.only(
                      bottomLeft: Radius.circular(0),
                      bottomRight: Radius.circular(0),
                      topLeft: Radius.circular(11),
                      topRight: Radius.circular(11),
                    ),
                  ),
                  child: Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(4, 2, 0, 0),
                    child: Text(
                      'SENHA',
                      style: FlutterFlowTheme.of(context).bodyMedium.override(
                            fontFamily: 'Rubik',
                            color: FlutterFlowTheme.of(context)
                                .secondaryBackground,
                            fontSize: 14,
                            letterSpacing: 0.5,
                            fontWeight: FontWeight.w600,
                          ),
                    ),
                  ),
                ),
              ),
              Container(
                width: 353,
                child: TextFormField(
                  controller: _model.senhaLoginTextController,
                  focusNode: _model.senhaLoginFocusNode,
                  autofocus: false,
                  obscureText: !_model.senhaLoginVisibility,
                  decoration: InputDecoration(
                    isDense: true,
                    labelStyle:
                        FlutterFlowTheme.of(context).labelMedium.override(
                              fontFamily: 'Inter',
                              letterSpacing: 0.0,
                            ),
                    hintStyle:
                        FlutterFlowTheme.of(context).labelMedium.override(
                              fontFamily: 'Inter',
                              letterSpacing: 0.0,
                            ),
                    enabledBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: Color(0x00000000),
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    focusedBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: Color(0x00000000),
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    errorBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: FlutterFlowTheme.of(context).error,
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    focusedErrorBorder: OutlineInputBorder(
                      borderSide: BorderSide(
                        color: FlutterFlowTheme.of(context).error,
                        width: 1,
                      ),
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    filled: true,
                    fillColor: FlutterFlowTheme.of(context).secondaryBackground,
                    suffixIcon: InkWell(
                      onTap: () => safeSetState(
                        () => _model.senhaLoginVisibility =
                            !_model.senhaLoginVisibility,
                      ),
                      focusNode: FocusNode(skipTraversal: true),
                      child: Icon(
                        _model.senhaLoginVisibility
                            ? Icons.visibility_outlined
                            : Icons.visibility_off_outlined,
                        size: 22,
                      ),
                    ),
                  ),
                  style: FlutterFlowTheme.of(context).bodyMedium.override(
                        fontFamily: 'Inter',
                        letterSpacing: 0.0,
                      ),
                  cursorColor: FlutterFlowTheme.of(context).primaryText,
                  validator: _model.senhaLoginTextControllerValidator
                      .asValidator(context),
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 16, 0, 0),
                child: FFButtonWidget(
                  onPressed: () async {
                    _model.resultadoLogin = await queryUsuariosRecordOnce(
                      queryBuilder: (usuariosRecord) => usuariosRecord
                          .where(
                            'email',
                            isEqualTo: _model.emailLoginTextController.text,
                          )
                          .where(
                            'confirmaSenha',
                            isEqualTo: _model.senhaLoginTextController.text,
                          ),
                      singleRecord: true,
                    ).then((s) => s.firstOrNull);
                    if (_model.resultadoLogin?.email != null &&
                        _model.resultadoLogin?.email != '') {
                      context.pushNamed('SaudeOla');
                    } else if (_model.resultadoLogin?.confirmaSenha != null &&
                        _model.resultadoLogin?.confirmaSenha != '') {
                    } else {
                      ScaffoldMessenger.of(context).showSnackBar(
                        SnackBar(
                          content: Text(
                            'Email ou senha inválidos. Tente novamente.',
                            style: TextStyle(
                              color: FlutterFlowTheme.of(context).primaryText,
                            ),
                          ),
                          duration: Duration(milliseconds: 4000),
                          backgroundColor: Color(0xFFAF1B14),
                        ),
                      );
                    }

                    safeSetState(() {});
                  },
                  text: 'Entrar',
                  options: FFButtonOptions(
                    width: 353,
                    height: 32,
                    padding: EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                    iconPadding: EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                    color: Color(0xFF246536),
                    textStyle: FlutterFlowTheme.of(context).titleSmall.override(
                          fontFamily: 'Rubik',
                          color: Colors.white,
                          fontSize: 18,
                          letterSpacing: 0.0,
                          fontWeight: FontWeight.w600,
                        ),
                    borderSide: BorderSide(
                      color: Colors.transparent,
                    ),
                    borderRadius: BorderRadius.only(
                      bottomLeft: Radius.circular(32),
                      bottomRight: Radius.circular(32),
                      topLeft: Radius.circular(32),
                      topRight: Radius.circular(32),
                    ),
                  ),
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 16, 0, 0),
                child: FFButtonWidget(
                  onPressed: () async {
                    context.pushNamed('SaudeCadasrtro');
                  },
                  text: 'Não é cadastrado? Clique aqui.',
                  options: FFButtonOptions(
                    width: 353,
                    height: 32,
                    padding: EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                    iconPadding: EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                    color: Color(0xFF246536),
                    textStyle: FlutterFlowTheme.of(context).titleSmall.override(
                          fontFamily: 'Rubik',
                          color: Colors.white,
                          fontSize: 20,
                          letterSpacing: 0.0,
                          fontWeight: FontWeight.w600,
                        ),
                    borderSide: BorderSide(
                      color: Colors.transparent,
                    ),
                    borderRadius: BorderRadius.only(
                      bottomLeft: Radius.circular(32),
                      bottomRight: Radius.circular(32),
                      topLeft: Radius.circular(32),
                      topRight: Radius.circular(32),
                    ),
                  ),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}


# **SaúdeCadastro**

import '/flutter_flow/flutter_flow_drop_down.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import '/flutter_flow/form_field_controller.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_cadasrtro_model.dart';
export 'saude_cadasrtro_model.dart';

class SaudeCadasrtroWidget extends StatefulWidget {
  const SaudeCadasrtroWidget({super.key});

  @override
  State<SaudeCadasrtroWidget> createState() => _SaudeCadasrtroWidgetState();
}

class _SaudeCadasrtroWidgetState extends State<SaudeCadasrtroWidget> {
  late SaudeCadasrtroModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeCadasrtroModel());

    _model.nomeTextController ??=
        TextEditingController(text: FFAppState().nome);
    _model.nomeFocusNode ??= FocusNode();

    _model.enderecoTextController ??=
        TextEditingController(text: FFAppState().endereco);
    _model.enderecoFocusNode ??= FocusNode();

    _model.numeroTextController ??=
        TextEditingController(text: FFAppState().numero);
    _model.numeroFocusNode ??= FocusNode();

    _model.complementoTextController ??=
        TextEditingController(text: FFAppState().complemento);
    _model.complementoFocusNode ??= FocusNode();

    _model.bairroTextController ??=
        TextEditingController(text: FFAppState().bairro);
    _model.bairroFocusNode ??= FocusNode();

    _model.cepTextController ??= TextEditingController(text: FFAppState().cep);
    _model.cepFocusNode ??= FocusNode();

    _model.cidadeTextController ??=
        TextEditingController(text: FFAppState().cidade);
    _model.cidadeFocusNode ??= FocusNode();

    _model.telefoneTextController ??=
        TextEditingController(text: FFAppState().telefone);
    _model.telefoneFocusNode ??= FocusNode();

    _model.emailTextController ??=
        TextEditingController(text: FFAppState().email);
    _model.emailFocusNode ??= FocusNode();

    _model.nascimentoTextController ??=
        TextEditingController(text: FFAppState().dataNascimento);
    _model.nascimentoFocusNode ??= FocusNode();

    _model.cpfTextController ??= TextEditingController(text: FFAppState().cpf);
    _model.cpfFocusNode ??= FocusNode();

    _model.senhaTextController ??=
        TextEditingController(text: FFAppState().senha);
    _model.senhaFocusNode ??= FocusNode();

    _model.oksenhaTextController ??=
        TextEditingController(text: FFAppState().confirmaSenha);
    _model.oksenhaFocusNode ??= FocusNode();
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    context.watch<FFAppState>();

    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: Colors.white,
        body: Container(
          width: 467,
          height: 962,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
              stops: [0, 1],
              begin: AlignmentDirectional(0, -1),
              end: AlignmentDirectional(0, 1),
            ),
            borderRadius: BorderRadius.only(
              bottomLeft: Radius.circular(32),
              bottomRight: Radius.circular(32),
              topLeft: Radius.circular(32),
              topRight: Radius.circular(32),
            ),
          ),
          child: Column(
            mainAxisSize: MainAxisSize.max,
            children: [
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 12),
                    child: ClipRRect(
                      borderRadius: BorderRadius.circular(8),
                      child: Image.asset(
                        'assets/images/Logo+Saude.png',
                        width: 70,
                        height: 70,
                        fit: BoxFit.cover,
                      ),
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(23, 70, 0, 0),
                    child: Container(
                      width: 244,
                      height: 28,
                      decoration: BoxDecoration(
                        color: Color(0xFF246536),
                        borderRadius: BorderRadius.only(
                          bottomLeft: Radius.circular(32),
                          bottomRight: Radius.circular(32),
                          topLeft: Radius.circular(32),
                          topRight: Radius.circular(32),
                        ),
                      ),
                      child: Text(
                        'NOVO CADASTRO',
                        textAlign: TextAlign.center,
                        style: FlutterFlowTheme.of(context).bodyMedium.override(
                              fontFamily: 'Inter',
                              color: Colors.white,
                              fontSize: 22,
                              letterSpacing: 0.0,
                              fontWeight: FontWeight.w600,
                            ),
                      ),
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 10, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 387,
                        height: 50,
                        decoration: BoxDecoration(),
                        child: Align(
                          alignment: AlignmentDirectional(2, 0),
                          child: Padding(
                            padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                            child: Column(
                              mainAxisSize: MainAxisSize.max,
                              children: [
                                Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 8, 0, 0),
                                  child: Container(
                                    width: 412,
                                    height: 16,
                                    decoration: BoxDecoration(
                                      color: Color(0xFF153A71),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(0),
                                        bottomRight: Radius.circular(0),
                                        topLeft: Radius.circular(11),
                                        topRight: Radius.circular(11),
                                      ),
                                    ),
                                    child: Padding(
                                      padding: EdgeInsetsDirectional.fromSTEB(
                                          4, 1, 0, 0),
                                      child: Text(
                                        'Nome',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color:
                                                  FlutterFlowTheme.of(context)
                                                      .secondaryBackground,
                                              fontSize: 12,
                                              letterSpacing: 0.5,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                  ),
                                ),
                                Expanded(
                                  child: Container(
                                    width: 410,
                                    child: TextFormField(
                                      controller: _model.nomeTextController,
                                      focusNode: _model.nomeFocusNode,
                                      autofocus: false,
                                      obscureText: false,
                                      decoration: InputDecoration(
                                        isDense: true,
                                        labelText: '\'',
                                        labelStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        hintStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        enabledBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 1,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 1,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        errorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 1,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedErrorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 1,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        filled: true,
                                        fillColor: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                      ),
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      cursorColor: FlutterFlowTheme.of(context)
                                          .primaryText,
                                      validator: _model
                                          .nomeTextControllerValidator
                                          .asValidator(context),
                                    ),
                                  ),
                                ),
                              ],
                            ),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 8, 0, 0),
                    child: Container(
                      width: 387,
                      height: 44,
                      decoration: BoxDecoration(),
                      child: Align(
                        alignment: AlignmentDirectional(2, 0),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 412,
                                height: 16,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 1, 0, 0),
                                  child: Text(
                                    'Endereço',
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: FlutterFlowTheme.of(context)
                                              .secondaryBackground,
                                          fontSize: 12,
                                          letterSpacing: 0.5,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Expanded(
                                child: Container(
                                  width: 410,
                                  child: TextFormField(
                                    controller: _model.enderecoTextController,
                                    focusNode: _model.enderecoFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .enderecoTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Align(
                alignment: AlignmentDirectional(0, -1),
                child: Padding(
                  padding: EdgeInsetsDirectional.fromSTEB(0, 4, 0, 0),
                  child: Row(
                    mainAxisSize: MainAxisSize.max,
                    crossAxisAlignment: CrossAxisAlignment.center,
                    children: [
                      Align(
                        alignment: AlignmentDirectional(0, 0),
                        child: Container(
                          height: 58,
                          decoration: BoxDecoration(),
                          child: Align(
                            alignment: AlignmentDirectional(-1, 0),
                            child: Column(
                              mainAxisSize: MainAxisSize.max,
                              children: [
                                Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 4, 0, 0),
                                  child: Container(
                                    width: 102,
                                    height: 16,
                                    decoration: BoxDecoration(
                                      color: Color(0xFF153A71),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(0),
                                        bottomRight: Radius.circular(0),
                                        topLeft: Radius.circular(11),
                                        topRight: Radius.circular(11),
                                      ),
                                    ),
                                    child: Padding(
                                      padding: EdgeInsetsDirectional.fromSTEB(
                                          3, 1, 0, 0),
                                      child: Text(
                                        'Número',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color:
                                                  FlutterFlowTheme.of(context)
                                                      .secondaryBackground,
                                              fontSize: 12,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                  ),
                                ),
                                Expanded(
                                  flex: 2,
                                  child: Align(
                                    alignment: AlignmentDirectional(-1, 0),
                                    child: Padding(
                                      padding: EdgeInsetsDirectional.fromSTEB(
                                          3, 0, 4, 12),
                                      child: Container(
                                        width: 101,
                                        child: TextFormField(
                                          controller:
                                              _model.numeroTextController,
                                          focusNode: _model.numeroFocusNode,
                                          autofocus: false,
                                          obscureText: false,
                                          decoration: InputDecoration(
                                            isDense: true,
                                            labelStyle:
                                                FlutterFlowTheme.of(context)
                                                    .labelMedium
                                                    .override(
                                                      fontFamily: 'Inter',
                                                      letterSpacing: 0.0,
                                                    ),
                                            hintStyle:
                                                FlutterFlowTheme.of(context)
                                                    .labelMedium
                                                    .override(
                                                      fontFamily: 'Inter',
                                                      letterSpacing: 0.0,
                                                    ),
                                            enabledBorder: OutlineInputBorder(
                                              borderSide: BorderSide(
                                                color: Color(0x00000000),
                                                width: 10,
                                              ),
                                              borderRadius: BorderRadius.only(
                                                bottomLeft: Radius.circular(17),
                                                bottomRight:
                                                    Radius.circular(17),
                                                topLeft: Radius.circular(0),
                                                topRight: Radius.circular(0),
                                              ),
                                            ),
                                            focusedBorder: OutlineInputBorder(
                                              borderSide: BorderSide(
                                                color: Color(0x00000000),
                                                width: 10,
                                              ),
                                              borderRadius: BorderRadius.only(
                                                bottomLeft: Radius.circular(17),
                                                bottomRight:
                                                    Radius.circular(17),
                                                topLeft: Radius.circular(0),
                                                topRight: Radius.circular(0),
                                              ),
                                            ),
                                            errorBorder: OutlineInputBorder(
                                              borderSide: BorderSide(
                                                color:
                                                    FlutterFlowTheme.of(context)
                                                        .error,
                                                width: 10,
                                              ),
                                              borderRadius: BorderRadius.only(
                                                bottomLeft: Radius.circular(17),
                                                bottomRight:
                                                    Radius.circular(17),
                                                topLeft: Radius.circular(0),
                                                topRight: Radius.circular(0),
                                              ),
                                            ),
                                            focusedErrorBorder:
                                                OutlineInputBorder(
                                              borderSide: BorderSide(
                                                color:
                                                    FlutterFlowTheme.of(context)
                                                        .error,
                                                width: 10,
                                              ),
                                              borderRadius: BorderRadius.only(
                                                bottomLeft: Radius.circular(17),
                                                bottomRight:
                                                    Radius.circular(17),
                                                topLeft: Radius.circular(0),
                                                topRight: Radius.circular(0),
                                              ),
                                            ),
                                            filled: true,
                                            fillColor:
                                                FlutterFlowTheme.of(context)
                                                    .secondaryBackground,
                                          ),
                                          style: FlutterFlowTheme.of(context)
                                              .bodyMedium
                                              .override(
                                                fontFamily: 'Inter',
                                                letterSpacing: 0.0,
                                              ),
                                          cursorColor:
                                              FlutterFlowTheme.of(context)
                                                  .primaryText,
                                          validator: _model
                                              .numeroTextControllerValidator
                                              .asValidator(context),
                                        ),
                                      ),
                                    ),
                                  ),
                                ),
                              ],
                            ),
                          ),
                        ),
                      ),
                      Align(
                        alignment: AlignmentDirectional(0, 0),
                        child: Container(
                          height: 58,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 4, 0, 0),
                                child: Container(
                                  width: 122,
                                  height: 16,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(11),
                                      topRight: Radius.circular(11),
                                    ),
                                  ),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        3, 1, 0, 0),
                                    child: Text(
                                      'Complemento',
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: FlutterFlowTheme.of(context)
                                                .secondaryBackground,
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                              Expanded(
                                flex: 2,
                                child: Align(
                                  alignment: AlignmentDirectional(-1, 0),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        0, 0, 0, 12),
                                    child: Container(
                                      width: 121,
                                      child: TextFormField(
                                        controller:
                                            _model.complementoTextController,
                                        focusNode: _model.complementoFocusNode,
                                        autofocus: false,
                                        obscureText: false,
                                        decoration: InputDecoration(
                                          isDense: true,
                                          labelStyle:
                                              FlutterFlowTheme.of(context)
                                                  .labelMedium
                                                  .override(
                                                    fontFamily: 'Inter',
                                                    letterSpacing: 0.0,
                                                  ),
                                          hintStyle:
                                              FlutterFlowTheme.of(context)
                                                  .labelMedium
                                                  .override(
                                                    fontFamily: 'Inter',
                                                    letterSpacing: 0.0,
                                                  ),
                                          enabledBorder: OutlineInputBorder(
                                            borderSide: BorderSide(
                                              color: Color(0x00000000),
                                              width: 10,
                                            ),
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(17),
                                              bottomRight: Radius.circular(17),
                                              topLeft: Radius.circular(0),
                                              topRight: Radius.circular(0),
                                            ),
                                          ),
                                          focusedBorder: OutlineInputBorder(
                                            borderSide: BorderSide(
                                              color: Color(0x00000000),
                                              width: 10,
                                            ),
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(17),
                                              bottomRight: Radius.circular(17),
                                              topLeft: Radius.circular(0),
                                              topRight: Radius.circular(0),
                                            ),
                                          ),
                                          errorBorder: OutlineInputBorder(
                                            borderSide: BorderSide(
                                              color:
                                                  FlutterFlowTheme.of(context)
                                                      .error,
                                              width: 10,
                                            ),
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(17),
                                              bottomRight: Radius.circular(17),
                                              topLeft: Radius.circular(0),
                                              topRight: Radius.circular(0),
                                            ),
                                          ),
                                          focusedErrorBorder:
                                              OutlineInputBorder(
                                            borderSide: BorderSide(
                                              color:
                                                  FlutterFlowTheme.of(context)
                                                      .error,
                                              width: 10,
                                            ),
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(17),
                                              bottomRight: Radius.circular(17),
                                              topLeft: Radius.circular(0),
                                              topRight: Radius.circular(0),
                                            ),
                                          ),
                                          filled: true,
                                          fillColor:
                                              FlutterFlowTheme.of(context)
                                                  .secondaryBackground,
                                        ),
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        cursorColor:
                                            FlutterFlowTheme.of(context)
                                                .primaryText,
                                        validator: _model
                                            .complementoTextControllerValidator
                                            .asValidator(context),
                                      ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                      Align(
                        alignment: AlignmentDirectional(0, 0),
                        child: Container(
                          height: 58,
                          decoration: BoxDecoration(),
                          child: Align(
                            alignment: AlignmentDirectional(0, 0),
                            child: Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(3, 0, 0, 0),
                              child: Column(
                                mainAxisSize: MainAxisSize.max,
                                children: [
                                  Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        0, 4, 0, 0),
                                    child: Container(
                                      width: 155,
                                      height: 16,
                                      decoration: BoxDecoration(
                                        color: Color(0xFF153A71),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(0),
                                          bottomRight: Radius.circular(0),
                                          topLeft: Radius.circular(11),
                                          topRight: Radius.circular(11),
                                        ),
                                      ),
                                      child: Padding(
                                        padding: EdgeInsetsDirectional.fromSTEB(
                                            3, 1, 0, 0),
                                        child: Text(
                                          'Bairro',
                                          style: FlutterFlowTheme.of(context)
                                              .bodyMedium
                                              .override(
                                                fontFamily: 'Rubik',
                                                color:
                                                    FlutterFlowTheme.of(context)
                                                        .secondaryBackground,
                                                fontSize: 12,
                                                letterSpacing: 0.0,
                                                fontWeight: FontWeight.w600,
                                              ),
                                        ),
                                      ),
                                    ),
                                  ),
                                  Expanded(
                                    flex: 3,
                                    child: Align(
                                      alignment: AlignmentDirectional(-1, 0),
                                      child: Padding(
                                        padding: EdgeInsetsDirectional.fromSTEB(
                                            1, 0, 0, 12),
                                        child: Container(
                                          width: 154,
                                          child: TextFormField(
                                            controller:
                                                _model.bairroTextController,
                                            focusNode: _model.bairroFocusNode,
                                            autofocus: false,
                                            obscureText: false,
                                            decoration: InputDecoration(
                                              isDense: true,
                                              labelStyle:
                                                  FlutterFlowTheme.of(context)
                                                      .labelMedium
                                                      .override(
                                                        fontFamily: 'Inter',
                                                        letterSpacing: 0.0,
                                                      ),
                                              hintStyle:
                                                  FlutterFlowTheme.of(context)
                                                      .labelMedium
                                                      .override(
                                                        fontFamily: 'Inter',
                                                        letterSpacing: 0.0,
                                                      ),
                                              enabledBorder: OutlineInputBorder(
                                                borderSide: BorderSide(
                                                  color: Color(0x00000000),
                                                  width: 10,
                                                ),
                                                borderRadius: BorderRadius.only(
                                                  bottomLeft:
                                                      Radius.circular(17),
                                                  bottomRight:
                                                      Radius.circular(17),
                                                  topLeft: Radius.circular(0),
                                                  topRight: Radius.circular(0),
                                                ),
                                              ),
                                              focusedBorder: OutlineInputBorder(
                                                borderSide: BorderSide(
                                                  color: Color(0x00000000),
                                                  width: 10,
                                                ),
                                                borderRadius: BorderRadius.only(
                                                  bottomLeft:
                                                      Radius.circular(17),
                                                  bottomRight:
                                                      Radius.circular(17),
                                                  topLeft: Radius.circular(0),
                                                  topRight: Radius.circular(0),
                                                ),
                                              ),
                                              errorBorder: OutlineInputBorder(
                                                borderSide: BorderSide(
                                                  color: FlutterFlowTheme.of(
                                                          context)
                                                      .error,
                                                  width: 10,
                                                ),
                                                borderRadius: BorderRadius.only(
                                                  bottomLeft:
                                                      Radius.circular(17),
                                                  bottomRight:
                                                      Radius.circular(17),
                                                  topLeft: Radius.circular(0),
                                                  topRight: Radius.circular(0),
                                                ),
                                              ),
                                              focusedErrorBorder:
                                                  OutlineInputBorder(
                                                borderSide: BorderSide(
                                                  color: FlutterFlowTheme.of(
                                                          context)
                                                      .error,
                                                  width: 10,
                                                ),
                                                borderRadius: BorderRadius.only(
                                                  bottomLeft:
                                                      Radius.circular(17),
                                                  bottomRight:
                                                      Radius.circular(17),
                                                  topLeft: Radius.circular(0),
                                                  topRight: Radius.circular(0),
                                                ),
                                              ),
                                              filled: true,
                                              fillColor:
                                                  FlutterFlowTheme.of(context)
                                                      .secondaryBackground,
                                            ),
                                            style: FlutterFlowTheme.of(context)
                                                .bodyMedium
                                                .override(
                                                  fontFamily: 'Inter',
                                                  letterSpacing: 0.0,
                                                ),
                                            cursorColor:
                                                FlutterFlowTheme.of(context)
                                                    .primaryText,
                                            validator: _model
                                                .bairroTextControllerValidator
                                                .asValidator(context),
                                          ),
                                        ),
                                      ),
                                    ),
                                  ),
                                ],
                              ),
                            ),
                          ),
                        ),
                      ),
                    ].addToStart(SizedBox(width: 2)),
                  ),
                ),
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      height: 58,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(2, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(2, 4, 0, 0),
                              child: Container(
                                width: 112,
                                height: 16,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      3, 1, 0, 0),
                                  child: Text(
                                    'CEP',
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: FlutterFlowTheme.of(context)
                                              .secondaryBackground,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                            Expanded(
                              flex: 2,
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      3, 0, 0, 12),
                                  child: Container(
                                    width: 111,
                                    child: TextFormField(
                                      controller: _model.cepTextController,
                                      focusNode: _model.cepFocusNode,
                                      autofocus: false,
                                      obscureText: false,
                                      decoration: InputDecoration(
                                        isDense: true,
                                        labelStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        hintStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        enabledBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        errorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedErrorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        filled: true,
                                        fillColor: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                      ),
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      cursorColor: FlutterFlowTheme.of(context)
                                          .primaryText,
                                      validator: _model
                                          .cepTextControllerValidator
                                          .asValidator(context),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      height: 58,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(2, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(3, 4, 0, 0),
                              child: Container(
                                width: 201,
                                height: 16,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      3, 1, 0, 0),
                                  child: Text(
                                    'Cidade',
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: FlutterFlowTheme.of(context)
                                              .secondaryBackground,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                            Expanded(
                              flex: 2,
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 0, 0, 12),
                                  child: Container(
                                    width: 200,
                                    child: TextFormField(
                                      controller: _model.cidadeTextController,
                                      focusNode: _model.cidadeFocusNode,
                                      autofocus: false,
                                      obscureText: false,
                                      decoration: InputDecoration(
                                        isDense: true,
                                        labelStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        hintStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        enabledBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        errorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedErrorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        filled: true,
                                        fillColor: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                      ),
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      cursorColor: FlutterFlowTheme.of(context)
                                          .primaryText,
                                      validator: _model
                                          .cidadeTextControllerValidator
                                          .asValidator(context),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Container(
                    height: 58,
                    decoration: BoxDecoration(),
                    child: Column(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(3, 4, 0, 0),
                          child: Container(
                            width: 59,
                            height: 16,
                            decoration: BoxDecoration(
                              color: Color(0xFF153A71),
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(0),
                                bottomRight: Radius.circular(0),
                                topLeft: Radius.circular(11),
                                topRight: Radius.circular(11),
                              ),
                            ),
                            child: Align(
                              alignment: AlignmentDirectional(-1, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(4, 1, 0, 0),
                                child: Text(
                                  'UF',
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                          ),
                        ),
                        Align(
                          alignment: AlignmentDirectional(0, 0),
                          child: Padding(
                            padding: EdgeInsetsDirectional.fromSTEB(2, 0, 0, 0),
                            child: Container(
                              width: 59,
                              height: 26,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(17),
                                  bottomRight: Radius.circular(17),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(1, 0),
                                child: FlutterFlowDropDown<String>(
                                  controller: _model.ufValueController ??=
                                      FormFieldController<String>(
                                    _model.ufValue ??= FFAppState().uf,
                                  ),
                                  options: List<String>.from([
                                    '1',
                                    'AC',
                                    'AL',
                                    'AP',
                                    'AM',
                                    'BA',
                                    'CE',
                                    'DF',
                                    'ES',
                                    'GO',
                                    'MA',
                                    'MT',
                                    'MS',
                                    'MG',
                                    'PA',
                                    'PB',
                                    'PR',
                                    'PE',
                                    'PI',
                                    'RJ',
                                    'RN',
                                    'RS',
                                    'RO',
                                    'RR',
                                    'SC',
                                    'SP',
                                    'SE',
                                    'TO'
                                  ]),
                                  optionLabels: [
                                    '',
                                    'AC',
                                    'AL',
                                    'AP',
                                    'AM',
                                    'BA',
                                    'CE',
                                    'DF',
                                    'ES',
                                    'GO',
                                    'MA',
                                    'MT',
                                    'MS',
                                    'MG',
                                    'PA',
                                    'PB',
                                    'PR',
                                    'PE',
                                    'PI',
                                    'RJ',
                                    'RN',
                                    'RS',
                                    'RO',
                                    'RR',
                                    'SC',
                                    'SP',
                                    'SE',
                                    'TO'
                                  ],
                                  onChanged: (val) =>
                                      safeSetState(() => _model.ufValue = val),
                                  width: 62,
                                  height: 30,
                                  textStyle: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Inter',
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w500,
                                      ),
                                  icon: Icon(
                                    Icons.keyboard_arrow_down_rounded,
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryText,
                                    size: 14,
                                  ),
                                  fillColor: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  elevation: 2,
                                  borderColor: Colors.transparent,
                                  borderWidth: 0,
                                  borderRadius: 12,
                                  margin: EdgeInsetsDirectional.fromSTEB(
                                      24, 0, 0, 0),
                                  hidesUnderline: true,
                                  isOverButton: false,
                                  isSearchable: false,
                                  isMultiSelect: false,
                                ),
                              ),
                            ),
                          ),
                        ),
                      ],
                    ),
                  ),
                ],
              ),
              Align(
                alignment: AlignmentDirectional(0, -1),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Container(
                      height: 58,
                      decoration: BoxDecoration(),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Container(
                            width: 146,
                            height: 16,
                            decoration: BoxDecoration(
                              color: Color(0xFF153A71),
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(0),
                                bottomRight: Radius.circular(0),
                                topLeft: Radius.circular(11),
                                topRight: Radius.circular(11),
                              ),
                            ),
                            child: Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(4, 1, 0, 0),
                              child: Text(
                                'Telefone',
                                style: FlutterFlowTheme.of(context)
                                    .bodyMedium
                                    .override(
                                      fontFamily: 'Rubik',
                                      color: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                      fontSize: 12,
                                      letterSpacing: 0.0,
                                      fontWeight: FontWeight.w600,
                                    ),
                              ),
                            ),
                          ),
                          Expanded(
                            flex: 2,
                            child: Align(
                              alignment: AlignmentDirectional(-1, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(4, 0, 8, 12),
                                child: Container(
                                  width: 145,
                                  child: TextFormField(
                                    controller: _model.telefoneTextController,
                                    focusNode: _model.telefoneFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .telefoneTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                    Container(
                      width: 235,
                      constraints: BoxConstraints(
                        maxHeight: 58,
                      ),
                      decoration: BoxDecoration(),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Align(
                            alignment: AlignmentDirectional(-1, 0),
                            child: Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(0, 0, 5, 0),
                              child: Container(
                                width: 231,
                                height: 16,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(-1, 0),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        3, 1, 0, 0),
                                    child: Text(
                                      'E-Mail',
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: FlutterFlowTheme.of(context)
                                                .secondaryBackground,
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ),
                          Expanded(
                            flex: 3,
                            child: Align(
                              alignment: AlignmentDirectional(-1, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 0, 8, 12),
                                child: Container(
                                  width: 230,
                                  child: TextFormField(
                                    controller: _model.emailTextController,
                                    focusNode: _model.emailFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .emailTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ],
                ),
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 0, 0, 1),
                    child: Container(
                      height: 58,
                      decoration: BoxDecoration(),
                      child: Align(
                        alignment: AlignmentDirectional(0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 141,
                              height: 16,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(3, 1, 0, 0),
                                child: Text(
                                  'Data de Nascimento',
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Expanded(
                              flex: 2,
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 8, 12),
                                  child: Container(
                                    width: 140,
                                    child: TextFormField(
                                      controller:
                                          _model.nascimentoTextController,
                                      focusNode: _model.nascimentoFocusNode,
                                      autofocus: false,
                                      obscureText: false,
                                      decoration: InputDecoration(
                                        isDense: true,
                                        labelStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        hintStyle: FlutterFlowTheme.of(context)
                                            .labelMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              letterSpacing: 0.0,
                                            ),
                                        enabledBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: Color(0x00000000),
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        errorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        focusedErrorBorder: OutlineInputBorder(
                                          borderSide: BorderSide(
                                            color: FlutterFlowTheme.of(context)
                                                .error,
                                            width: 10,
                                          ),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(17),
                                            bottomRight: Radius.circular(17),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                        filled: true,
                                        fillColor: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                      ),
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      cursorColor: FlutterFlowTheme.of(context)
                                          .primaryText,
                                      validator: _model
                                          .nascimentoTextControllerValidator
                                          .asValidator(context),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 0, 0, 1),
                    child: Container(
                      width: 70,
                      height: 58,
                      decoration: BoxDecoration(),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Align(
                            alignment: AlignmentDirectional(0, 0),
                            child: Column(
                              mainAxisSize: MainAxisSize.max,
                              children: [
                                Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 0, 7, 0),
                                  child: Container(
                                    width: 71,
                                    height: 16,
                                    decoration: BoxDecoration(
                                      color: Color(0xFF153A71),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(0),
                                        bottomRight: Radius.circular(0),
                                        topLeft: Radius.circular(11),
                                        topRight: Radius.circular(11),
                                      ),
                                    ),
                                    child: Padding(
                                      padding: EdgeInsetsDirectional.fromSTEB(
                                          3, 1, 0, 0),
                                      child: Text(
                                        'Sexo',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color:
                                                  FlutterFlowTheme.of(context)
                                                      .secondaryBackground,
                                              fontSize: 12,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                  ),
                                ),
                              ],
                            ),
                          ),
                          Align(
                            alignment: AlignmentDirectional(-1, 0),
                            child: Container(
                              width: 62,
                              height: 30,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(17),
                                  bottomRight: Radius.circular(17),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(0, 0),
                                child: FlutterFlowDropDown<String>(
                                  controller: _model.sexoValueController ??=
                                      FormFieldController<String>(
                                    _model.sexoValue ??= FFAppState().sexo,
                                  ),
                                  options: List<String>.from(['1', 'M', 'F']),
                                  optionLabels: ['', 'M', 'F'],
                                  onChanged: (val) => safeSetState(
                                      () => _model.sexoValue = val),
                                  width: 62,
                                  height: 30,
                                  textStyle: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Inter',
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w500,
                                      ),
                                  icon: Icon(
                                    Icons.keyboard_arrow_down_rounded,
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryText,
                                    size: 14,
                                  ),
                                  fillColor: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  elevation: 2,
                                  borderColor: Colors.transparent,
                                  borderWidth: 0,
                                  borderRadius: 12,
                                  margin: EdgeInsetsDirectional.fromSTEB(
                                      24, 0, 0, 0),
                                  hidesUnderline: true,
                                  isOverButton: false,
                                  isSearchable: false,
                                  isMultiSelect: false,
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 0, 0, 1),
                    child: Container(
                      width: 168,
                      height: 58,
                      decoration: BoxDecoration(),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Padding(
                            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 6, 0),
                            child: Container(
                              width: 165,
                              height: 16,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(3, 1, 0, 0),
                                child: Text(
                                  'CPF',
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                          ),
                          Expanded(
                            flex: 2,
                            child: Align(
                              alignment: AlignmentDirectional(-1, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 0, 8, 12),
                                child: Container(
                                  width: 164,
                                  child: TextFormField(
                                    controller: _model.cpfTextController,
                                    focusNode: _model.cpfFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 10,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model.cpfTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Container(
                    width: 387,
                    height: 44,
                    decoration: BoxDecoration(),
                    child: Align(
                      alignment: AlignmentDirectional(2, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 412,
                              height: 16,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(4, 1, 0, 0),
                                child: Text(
                                  'Defina a Senha',
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        fontSize: 12,
                                        letterSpacing: 0.5,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Expanded(
                              child: Container(
                                width: 410,
                                child: TextFormField(
                                  controller: _model.senhaTextController,
                                  focusNode: _model.senhaFocusNode,
                                  autofocus: false,
                                  obscureText: false,
                                  decoration: InputDecoration(
                                    isDense: true,
                                    labelStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    hintStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    enabledBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(17),
                                        bottomRight: Radius.circular(17),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(17),
                                        bottomRight: Radius.circular(17),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    errorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(17),
                                        bottomRight: Radius.circular(17),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedErrorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(17),
                                        bottomRight: Radius.circular(17),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    filled: true,
                                    fillColor: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                  ),
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Inter',
                                        letterSpacing: 0.0,
                                      ),
                                  cursorColor:
                                      FlutterFlowTheme.of(context).primaryText,
                                  validator: _model.senhaTextControllerValidator
                                      .asValidator(context),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 8, 0, 0),
                    child: Container(
                      width: 387,
                      height: 44,
                      decoration: BoxDecoration(),
                      child: Align(
                        alignment: AlignmentDirectional(2, 0),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 412,
                                height: 16,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 1, 0, 0),
                                  child: Text(
                                    'Confirme a Senha ',
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: FlutterFlowTheme.of(context)
                                              .secondaryBackground,
                                          fontSize: 12,
                                          letterSpacing: 0.5,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Expanded(
                                child: Container(
                                  width: 410,
                                  child: TextFormField(
                                    controller: _model.oksenhaTextController,
                                    focusNode: _model.oksenhaFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .oksenhaTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 16, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(34, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          context.pushNamed('SaudeLogin');
                        },
                        text: 'Voltar',
                        options: FFButtonOptions(
                          width: 95,
                          height: 19,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Inter Tight',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(32),
                            bottomRight: Radius.circular(32),
                            topLeft: Radius.circular(32),
                            topRight: Radius.circular(32),
                          ),
                        ),
                      ),
                    ),
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(144, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          FFAppState().nome = _model.nomeTextController.text;
                          safeSetState(() {});
                          FFAppState().endereco =
                              _model.enderecoTextController.text;
                          safeSetState(() {});
                          FFAppState().numero =
                              _model.numeroTextController.text;
                          safeSetState(() {});
                          FFAppState().complemento =
                              _model.complementoTextController.text;
                          safeSetState(() {});
                          FFAppState().bairro =
                              _model.bairroTextController.text;
                          safeSetState(() {});
                          FFAppState().cep = _model.cepTextController.text;
                          safeSetState(() {});
                          FFAppState().cidade =
                              _model.cidadeTextController.text;
                          safeSetState(() {});
                          FFAppState().uf = _model.ufValue!;
                          safeSetState(() {});
                          FFAppState().telefone =
                              _model.telefoneTextController.text;
                          safeSetState(() {});
                          FFAppState().email = _model.emailTextController.text;
                          safeSetState(() {});
                          FFAppState().dataNascimento =
                              _model.nascimentoTextController.text;
                          safeSetState(() {});
                          FFAppState().sexo = _model.sexoValue!;
                          safeSetState(() {});
                          FFAppState().cpf = _model.cpfTextController.text;
                          safeSetState(() {});
                          FFAppState().senha = _model.senhaTextController.text;
                          safeSetState(() {});
                          FFAppState().confirmaSenha =
                              _model.oksenhaTextController.text;
                          safeSetState(() {});

                          context.pushNamed('SaudeCadastro2');
                        },
                        text: 'Próximo',
                        options: FFButtonOptions(
                          width: 95,
                          height: 19,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Inter Tight',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(32),
                            bottomRight: Radius.circular(32),
                            topLeft: Radius.circular(32),
                            topRight: Radius.circular(32),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

# **Saúde Cadastro2**

import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_cadastro2_model.dart';
export 'saude_cadastro2_model.dart';

class SaudeCadastro2Widget extends StatefulWidget {
  const SaudeCadastro2Widget({super.key});

  @override
  State<SaudeCadastro2Widget> createState() => _SaudeCadastro2WidgetState();
}

class _SaudeCadastro2WidgetState extends State<SaudeCadastro2Widget> {
  late SaudeCadastro2Model _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeCadastro2Model());

    _model.qualProblemaTextController ??=
        TextEditingController(text: FFAppState().descricaoProblema);
    _model.qualProblemaFocusNode ??= FocusNode();

    _model.qualRemedioTextController ??=
        TextEditingController(text: FFAppState().qualRemedio);
    _model.qualRemedioFocusNode ??= FocusNode();

    _model.qualFilhoNaoTextController ??=
        TextEditingController(text: FFAppState().qualAnticoncepicional);
    _model.qualFilhoNaoFocusNode ??= FocusNode();

    _model.qualAlergiaTextController ??=
        TextEditingController(text: FFAppState().qualMedAlergia);
    _model.qualAlergiaFocusNode ??= FocusNode();

    _model.qualCirurgiaTextController ??=
        TextEditingController(text: FFAppState().qualCirurgia);
    _model.qualCirurgiaFocusNode ??= FocusNode();

    _model.qualTratoTextController ??=
        TextEditingController(text: FFAppState().qualTratamento);
    _model.qualTratoFocusNode ??= FocusNode();
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    context.watch<FFAppState>();

    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Container(
          width: 462,
          height: 967,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
              stops: [0, 1],
              begin: AlignmentDirectional(0, -1),
              end: AlignmentDirectional(0, 1),
            ),
            borderRadius: BorderRadius.only(
              bottomLeft: Radius.circular(32),
              bottomRight: Radius.circular(32),
              topLeft: Radius.circular(32),
              topRight: Radius.circular(32),
            ),
          ),
          child: Column(
            mainAxisSize: MainAxisSize.max,
            children: [
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 12),
                    child: ClipRRect(
                      borderRadius: BorderRadius.circular(8),
                      child: Image.asset(
                        'assets/images/Logo+Saude.png',
                        width: 70,
                        height: 70,
                        fit: BoxFit.cover,
                      ),
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(22, 70, 0, 0),
                    child: Container(
                      width: 244,
                      height: 28,
                      decoration: BoxDecoration(
                        color: Color(0xFF246536),
                        borderRadius: BorderRadius.only(
                          bottomLeft: Radius.circular(32),
                          bottomRight: Radius.circular(32),
                          topLeft: Radius.circular(32),
                          topRight: Radius.circular(32),
                        ),
                      ),
                      child: Text(
                        'NOVO CADASTRO',
                        textAlign: TextAlign.center,
                        style: FlutterFlowTheme.of(context).bodyMedium.override(
                              fontFamily: 'Inter',
                              color: Colors.white,
                              fontSize: 22,
                              letterSpacing: 0.0,
                              fontWeight: FontWeight.w600,
                            ),
                      ),
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 44, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  mainAxisAlignment: MainAxisAlignment.start,
                  children: [
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        2, 0, 0, 0),
                                    child: Text(
                                      'Tem algum problema de Saúde?',
                                      textAlign: TextAlign.start,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'SIM',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 100,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.temProblesimValue ??=
                                        FFAppState().temProblema,
                                    onChanged: (newValue) async {
                                      safeSetState(() =>
                                          _model.temProblesimValue = newValue!);
                                      if (newValue!) {
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.temProblenaoValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'NÃO',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.temProblenaoValue ??=
                                        FFAppState().temProblemaNao,
                                    onChanged: (newValue) async {
                                      safeSetState(() =>
                                          _model.temProblenaoValue = newValue!);
                                      if (newValue!) {
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.temProblesimValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      6, 0, 0, 0),
                                  child: Text(
                                    'Se sim, qual?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 13,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                child: Container(
                                  width: 168,
                                  child: TextFormField(
                                    controller:
                                        _model.qualProblemaTextController,
                                    focusNode: _model.qualProblemaFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 11,
                                            letterSpacing: 0.2,
                                            fontWeight: FontWeight.bold,
                                            lineHeight: 13,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .qualProblemaTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 4, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  mainAxisAlignment: MainAxisAlignment.start,
                  children: [
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        2, 0, 0, 0),
                                    child: Text(
                                      'Toma algum remédio?',
                                      textAlign: TextAlign.start,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'SIM',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.tomaRemedioValue ??=
                                        FFAppState().tomaRemedio,
                                    onChanged: (newValue) async {
                                      safeSetState(() =>
                                          _model.tomaRemedioValue = newValue!);
                                      if (newValue!) {
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.naoTomaRemedioValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'NÃO',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.naoTomaRemedioValue ??=
                                        FFAppState().tomaRemedioNao,
                                    onChanged: (newValue) async {
                                      safeSetState(() => _model
                                          .naoTomaRemedioValue = newValue!);
                                      if (newValue!) {
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.tomaRemedioValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      6, 0, 0, 0),
                                  child: Text(
                                    'Se sim, qual?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 13,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                child: Container(
                                  width: 168,
                                  child: TextFormField(
                                    controller:
                                        _model.qualRemedioTextController,
                                    focusNode: _model.qualRemedioFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 11,
                                            letterSpacing: 0.2,
                                            fontWeight: FontWeight.bold,
                                            lineHeight: 13,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .qualRemedioTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 4, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  mainAxisAlignment: MainAxisAlignment.start,
                  children: [
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Text(
                                    'Toma anticoncepcional?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 11,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'SIM',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.filhoNaoValue ??=
                                        FFAppState().tomaAnticoncepicional,
                                    onChanged: (newValue) async {
                                      safeSetState(() =>
                                          _model.filhoNaoValue = newValue!);
                                      if (newValue!) {
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.filhoSimValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'NÃO',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.filhoSimValue ??=
                                        FFAppState().tomaAnticoncepicionalNao,
                                    onChanged: (newValue) async {
                                      safeSetState(() =>
                                          _model.filhoSimValue = newValue!);
                                      if (newValue!) {
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.filhoNaoValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      6, 0, 0, 0),
                                  child: Text(
                                    'Se sim, qual?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 13,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                child: Container(
                                  width: 168,
                                  child: TextFormField(
                                    controller:
                                        _model.qualFilhoNaoTextController,
                                    focusNode: _model.qualFilhoNaoFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 11,
                                            letterSpacing: 0.2,
                                            fontWeight: FontWeight.bold,
                                            lineHeight: 13,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .qualFilhoNaoTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 4, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  mainAxisAlignment: MainAxisAlignment.start,
                  children: [
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        2, 0, 0, 0),
                                    child: Text(
                                      'Tem alergia a algum medicamento?',
                                      textAlign: TextAlign.start,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'SIM',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.alergiaSimValue ??=
                                        FFAppState().temAlergia,
                                    onChanged: (newValue) async {
                                      safeSetState(() =>
                                          _model.alergiaSimValue = newValue!);
                                      if (newValue!) {
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.alergiaNaoValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'NÃO',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.alergiaNaoValue ??=
                                        FFAppState().temAlergiaNao,
                                    onChanged: (newValue) async {
                                      safeSetState(() =>
                                          _model.alergiaNaoValue = newValue!);
                                      if (newValue!) {
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.alergiaSimValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 145,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 169,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      6, 0, 0, 0),
                                  child: Text(
                                    'Se sim, qual?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 13,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                child: Container(
                                  width: 168,
                                  child: TextFormField(
                                    controller:
                                        _model.qualAlergiaTextController,
                                    focusNode: _model.qualAlergiaFocusNode,
                                    autofocus: false,
                                    obscureText: false,
                                    decoration: InputDecoration(
                                      isDense: true,
                                      labelStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 11,
                                            letterSpacing: 0.2,
                                            fontWeight: FontWeight.bold,
                                            lineHeight: 13,
                                          ),
                                      hintStyle: FlutterFlowTheme.of(context)
                                          .labelMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                      enabledBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: Color(0x00000000),
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      errorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      focusedErrorBorder: OutlineInputBorder(
                                        borderSide: BorderSide(
                                          color: FlutterFlowTheme.of(context)
                                              .error,
                                          width: 1,
                                        ),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(11),
                                          bottomRight: Radius.circular(11),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      filled: true,
                                      fillColor: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                    ),
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    cursorColor: FlutterFlowTheme.of(context)
                                        .primaryText,
                                    validator: _model
                                        .qualAlergiaTextControllerValidator
                                        .asValidator(context),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 145,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 169,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(0, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      2, 0, 0, 0),
                                  child: Text(
                                    'Ja fez alguma cirurgia?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.cirurgiaSimValue ??=
                                      FFAppState().fezCirurgia,
                                  onChanged: (newValue) async {
                                    safeSetState(() =>
                                        _model.cirurgiaSimValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.cirurgiaNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.cirurgiaNaoValue ??=
                                      FFAppState().fezCirurgiaNao,
                                  onChanged: (newValue) async {
                                    safeSetState(() =>
                                        _model.cirurgiaNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.cirurgiaSimValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 145,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 169,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                                child: Text(
                                  'Se sim, qual?',
                                  textAlign: TextAlign.start,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 13,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              child: Container(
                                width: 168,
                                child: TextFormField(
                                  controller: _model.qualCirurgiaTextController,
                                  focusNode: _model.qualCirurgiaFocusNode,
                                  autofocus: false,
                                  obscureText: false,
                                  decoration: InputDecoration(
                                    isDense: true,
                                    labelStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 11,
                                          letterSpacing: 0.2,
                                          fontWeight: FontWeight.bold,
                                          lineHeight: 13,
                                        ),
                                    hintStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                    enabledBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    errorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedErrorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    filled: true,
                                    fillColor: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                  ),
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Inter',
                                        letterSpacing: 0.0,
                                      ),
                                  cursorColor:
                                      FlutterFlowTheme.of(context).primaryText,
                                  validator: _model
                                      .qualCirurgiaTextControllerValidator
                                      .asValidator(context),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 145,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 169,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(0, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      2, 0, 0, 0),
                                  child: Text(
                                    'Faz tratamento médico?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.trataSimValue ??=
                                      FFAppState().fazTratamento,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.trataSimValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.trataNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.trataNaoValue ??=
                                      FFAppState().fazTratamentoNao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.trataNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.trataSimValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 145,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 169,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                                child: Text(
                                  'Se sim, qual?',
                                  textAlign: TextAlign.start,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 13,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              child: Container(
                                width: 168,
                                child: TextFormField(
                                  controller: _model.qualTratoTextController,
                                  focusNode: _model.qualTratoFocusNode,
                                  autofocus: false,
                                  obscureText: false,
                                  decoration: InputDecoration(
                                    isDense: true,
                                    labelStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 11,
                                          letterSpacing: 0.2,
                                          fontWeight: FontWeight.bold,
                                          lineHeight: 13,
                                        ),
                                    hintStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                    enabledBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    errorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedErrorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    filled: true,
                                    fillColor: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                  ),
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Inter',
                                        letterSpacing: 0.0,
                                      ),
                                  cursorColor:
                                      FlutterFlowTheme.of(context).primaryText,
                                  validator: _model
                                      .qualTratoTextControllerValidator
                                      .asValidator(context),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 46, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(40, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          FFAppState().temProblema = valueOrDefault<bool>(
                            _model.temProblesimValue,
                            false,
                          );
                          safeSetState(() {});
                          FFAppState().temProblemaNao =
                              _model.temProblenaoValue!;
                          safeSetState(() {});
                          FFAppState().descricaoProblema =
                              _model.qualProblemaTextController.text;
                          safeSetState(() {});
                          FFAppState().tomaRemedio = _model.tomaRemedioValue!;
                          safeSetState(() {});
                          FFAppState().tomaRemedioNao =
                              _model.naoTomaRemedioValue!;
                          safeSetState(() {});
                          FFAppState().qualRemedio =
                              _model.qualRemedioTextController.text;
                          safeSetState(() {});
                          FFAppState().tomaAnticoncepicional =
                              _model.filhoNaoValue!;
                          safeSetState(() {});
                          FFAppState().tomaAnticoncepicionalNao =
                              _model.filhoSimValue!;
                          safeSetState(() {});
                          FFAppState().qualAnticoncepicional =
                              _model.qualFilhoNaoTextController.text;
                          safeSetState(() {});
                          FFAppState().temAlergia = _model.alergiaSimValue!;
                          safeSetState(() {});
                          FFAppState().temAlergiaNao = _model.alergiaNaoValue!;
                          safeSetState(() {});
                          FFAppState().qualMedAlergia =
                              _model.qualAlergiaTextController.text;
                          safeSetState(() {});
                          FFAppState().fezCirurgia = _model.cirurgiaSimValue!;
                          safeSetState(() {});
                          FFAppState().fezCirurgiaNao =
                              _model.cirurgiaNaoValue!;
                          safeSetState(() {});
                          FFAppState().qualCirurgia =
                              _model.qualCirurgiaTextController.text;
                          safeSetState(() {});
                          FFAppState().fazTratamento = _model.trataSimValue!;
                          safeSetState(() {});
                          FFAppState().fazTratamentoNao = _model.trataNaoValue!;
                          safeSetState(() {});
                          FFAppState().qualTratamento =
                              _model.qualTratoTextController.text;
                          safeSetState(() {});

                          context.pushNamed('SaudeCadasrtro');
                        },
                        text: 'Voltar',
                        options: FFButtonOptions(
                          width: 95,
                          height: 19,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Inter Tight',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(32),
                            bottomRight: Radius.circular(32),
                            topLeft: Radius.circular(32),
                            topRight: Radius.circular(32),
                          ),
                        ),
                      ),
                    ),
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(128, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          FFAppState().temProblema = valueOrDefault<bool>(
                            _model.temProblesimValue,
                            false,
                          );
                          safeSetState(() {});
                          FFAppState().temProblemaNao =
                              _model.temProblenaoValue!;
                          safeSetState(() {});
                          FFAppState().descricaoProblema =
                              _model.qualProblemaTextController.text;
                          safeSetState(() {});
                          FFAppState().tomaRemedio = _model.tomaRemedioValue!;
                          safeSetState(() {});
                          FFAppState().tomaRemedioNao =
                              _model.naoTomaRemedioValue!;
                          safeSetState(() {});
                          FFAppState().qualRemedio =
                              _model.qualRemedioTextController.text;
                          safeSetState(() {});
                          FFAppState().tomaAnticoncepicional =
                              _model.filhoNaoValue!;
                          safeSetState(() {});
                          FFAppState().tomaAnticoncepicionalNao =
                              _model.filhoSimValue!;
                          safeSetState(() {});
                          FFAppState().qualAnticoncepicional =
                              _model.qualFilhoNaoTextController.text;
                          safeSetState(() {});
                          FFAppState().temAlergia = _model.alergiaSimValue!;
                          safeSetState(() {});
                          FFAppState().temAlergiaNao = _model.alergiaNaoValue!;
                          safeSetState(() {});
                          FFAppState().qualMedAlergia =
                              _model.qualAlergiaTextController.text;
                          safeSetState(() {});
                          FFAppState().fezCirurgia = _model.cirurgiaSimValue!;
                          safeSetState(() {});
                          FFAppState().fezCirurgiaNao =
                              _model.cirurgiaNaoValue!;
                          safeSetState(() {});
                          FFAppState().qualCirurgia =
                              _model.qualCirurgiaTextController.text;
                          safeSetState(() {});
                          FFAppState().fazTratamento = _model.trataSimValue!;
                          safeSetState(() {});
                          FFAppState().fazTratamentoNao = _model.trataNaoValue!;
                          safeSetState(() {});
                          FFAppState().qualTratamento =
                              _model.qualTratoTextController.text;
                          safeSetState(() {});

                          context.pushNamed('SaudeCadastro3');
                        },
                        text: 'Próximo',
                        options: FFButtonOptions(
                          width: 95,
                          height: 19,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Inter Tight',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(32),
                            bottomRight: Radius.circular(32),
                            topLeft: Radius.circular(32),
                            topRight: Radius.circular(32),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

# **Saúde Cadastro3** 

import '/backend/backend.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:cloud_firestore/cloud_firestore.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_cadastro3_model.dart';
export 'saude_cadastro3_model.dart';

class SaudeCadastro3Widget extends StatefulWidget {
  const SaudeCadastro3Widget({super.key});

  @override
  State<SaudeCadastro3Widget> createState() => _SaudeCadastro3WidgetState();
}

class _SaudeCadastro3WidgetState extends State<SaudeCadastro3Widget> {
  late SaudeCadastro3Model _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeCadastro3Model());

    _model.outroProblemaTextController ??=
        TextEditingController(text: FFAppState().outroProblNListado);
    _model.outroProblemaFocusNode ??= FocusNode();
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    context.watch<FFAppState>();

    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Container(
          width: 462,
          height: 967,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
              stops: [0, 1],
              begin: AlignmentDirectional(0, -1),
              end: AlignmentDirectional(0, 1),
            ),
            borderRadius: BorderRadius.only(
              bottomLeft: Radius.circular(32),
              bottomRight: Radius.circular(32),
              topLeft: Radius.circular(32),
              topRight: Radius.circular(32),
            ),
          ),
          child: Column(
            mainAxisSize: MainAxisSize.max,
            children: [
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 12),
                    child: ClipRRect(
                      borderRadius: BorderRadius.circular(8),
                      child: Image.asset(
                        'assets/images/Logo+Saude.png',
                        width: 70,
                        height: 70,
                        fit: BoxFit.cover,
                      ),
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(22, 70, 0, 0),
                    child: Container(
                      width: 244,
                      height: 28,
                      decoration: BoxDecoration(
                        color: Color(0xFF246536),
                        borderRadius: BorderRadius.only(
                          bottomLeft: Radius.circular(32),
                          bottomRight: Radius.circular(32),
                          topLeft: Radius.circular(32),
                          topRight: Radius.circular(32),
                        ),
                      ),
                      child: Text(
                        'NOVO CADASTRO',
                        textAlign: TextAlign.center,
                        style: FlutterFlowTheme.of(context).bodyMedium.override(
                              fontFamily: 'Inter',
                              color: Colors.white,
                              fontSize: 22,
                              letterSpacing: 0.0,
                              fontWeight: FontWeight.w600,
                            ),
                      ),
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 44, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  mainAxisAlignment: MainAxisAlignment.start,
                  children: [
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Container(
                        width: 266,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 269,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                              ),
                              Container(
                                width: 265,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(-1, 0),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        4, 0, 0, 0),
                                    child: Text(
                                      'Esta gestante?',
                                      textAlign: TextAlign.start,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Color(0xFF153A71),
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'SIM',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.maeSimValue ??=
                                        FFAppState().gestante,
                                    onChanged: (newValue) async {
                                      safeSetState(
                                          () => _model.maeSimValue = newValue!);
                                      if (newValue!) {
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.maeNaoValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                        child: Container(
                          width: 44,
                          height: 60,
                          decoration: BoxDecoration(),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 44,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 1, 0, 0),
                                  child: Text(
                                    'NÃO',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 165,
                                height: 35,
                                decoration: BoxDecoration(
                                  color: Colors.white,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(11),
                                    bottomRight: Radius.circular(11),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Theme(
                                  data: ThemeData(
                                    checkboxTheme: CheckboxThemeData(
                                      visualDensity: VisualDensity.compact,
                                      materialTapTargetSize:
                                          MaterialTapTargetSize.shrinkWrap,
                                      shape: RoundedRectangleBorder(
                                        borderRadius: BorderRadius.circular(4),
                                      ),
                                    ),
                                    unselectedWidgetColor:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  child: Checkbox(
                                    value: _model.maeNaoValue ??=
                                        FFAppState().gestanteNao,
                                    onChanged: (newValue) async {
                                      safeSetState(
                                          () => _model.maeNaoValue = newValue!);
                                      if (newValue!) {
                                        _model.checkNao = false;
                                        safeSetState(() {});
                                        _model.checkSim = true;
                                        safeSetState(() {});
                                        safeSetState(() {
                                          _model.maeSimValue = false;
                                        });
                                      }
                                    },
                                    side: BorderSide(
                                      width: 2,
                                      color: FlutterFlowTheme.of(context)
                                          .alternate,
                                    ),
                                    activeColor:
                                        FlutterFlowTheme.of(context).primary,
                                    checkColor:
                                        FlutterFlowTheme.of(context).info,
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 266,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 269,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 265,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 0, 0),
                                  child: Text(
                                    'Problema no figado?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.figadoRValue ??=
                                      FFAppState().problemaFigadoRim,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.figadoRValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.figadoBValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.figadoBValue ??=
                                      FFAppState().bomFigadoRim,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.figadoBValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.figadoRValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 266,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 269,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 265,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 0, 0),
                                  child: Text(
                                    'Você é fumante?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.fumaValue ??=
                                      FFAppState().fumante,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.fumaValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.fumaNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.fumaNaoValue ??=
                                      FFAppState().fumanteNao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.fumaNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.fumaValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 266,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 269,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 265,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 0, 0),
                                  child: Text(
                                    'Você ja teve hepatite?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.titeSimValue ??=
                                      FFAppState().teveHepatite,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.titeSimValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.titeNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.titeNaoValue ??=
                                      FFAppState().teveHepatiteNao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.titeNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.titeSimValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 266,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 269,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 265,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 0, 0),
                                  child: Text(
                                    'Tem diabétes?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.doceSimValue ??=
                                      FFAppState().diabetes,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.doceSimValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.doceNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.doceNaoValue ??=
                                      FFAppState().diabetesNao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.doceNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.doceSimValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 266,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 269,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 265,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 0, 0),
                                  child: Text(
                                    'Tem asma?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.asmaSimValue ??=
                                      FFAppState().asma,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.asmaSimValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.asmaNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.asmaNaoValue ??=
                                      FFAppState().asmaNao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.asmaNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.asmaSimValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 266,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 269,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 265,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 0, 0),
                                  child: Text(
                                    'Tem problema cardíaco?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.morreSimValue ??=
                                      FFAppState().problemaCoracao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.morreSimValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.morreNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.morreNaoValue ??=
                                      FFAppState().problemaCoracaoNao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.morreNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.morreSimValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 266,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(4, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 269,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                            ),
                            Container(
                              width: 265,
                              height: 35,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-1, 0),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 0, 0, 0),
                                  child: Text(
                                    'Tem problema renal?',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'SIM',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.rimSimValue ??=
                                      FFAppState().problemaRenal,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.rimSimValue = newValue!);
                                    if (newValue!) {
                                      _model.checkSim = true;
                                      safeSetState(() {});
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.rimNaoValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                      child: Container(
                        width: 44,
                        height: 60,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Container(
                              width: 44,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(11),
                                  topRight: Radius.circular(11),
                                ),
                              ),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 1, 0, 0),
                                child: Text(
                                  'NÃO',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                            Container(
                              width: 165,
                              height: 35,
                              decoration: BoxDecoration(
                                color: Colors.white,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(11),
                                  bottomRight: Radius.circular(11),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Theme(
                                data: ThemeData(
                                  checkboxTheme: CheckboxThemeData(
                                    visualDensity: VisualDensity.compact,
                                    materialTapTargetSize:
                                        MaterialTapTargetSize.shrinkWrap,
                                    shape: RoundedRectangleBorder(
                                      borderRadius: BorderRadius.circular(4),
                                    ),
                                  ),
                                  unselectedWidgetColor:
                                      FlutterFlowTheme.of(context).alternate,
                                ),
                                child: Checkbox(
                                  value: _model.rimNaoValue ??=
                                      FFAppState().problemaRenalNao,
                                  onChanged: (newValue) async {
                                    safeSetState(
                                        () => _model.rimNaoValue = newValue!);
                                    if (newValue!) {
                                      _model.checkNao = false;
                                      safeSetState(() {});
                                      _model.checkSim = false;
                                      safeSetState(() {});
                                      safeSetState(() {
                                        _model.rimSimValue = false;
                                      });
                                    }
                                  },
                                  side: BorderSide(
                                    width: 2,
                                    color:
                                        FlutterFlowTheme.of(context).alternate,
                                  ),
                                  activeColor:
                                      FlutterFlowTheme.of(context).primary,
                                  checkColor: FlutterFlowTheme.of(context).info,
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Container(
                      width: 381,
                      height: 60,
                      decoration: BoxDecoration(),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(0, 4, 0, 0),
                              child: Container(
                                width: 412,
                                height: 16,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(11),
                                    topRight: Radius.circular(11),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      4, 1, 0, 0),
                                  child: Text(
                                    'Insira um outro problema que você tem e não esta listado aqui.',
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: FlutterFlowTheme.of(context)
                                              .secondaryBackground,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                            Container(
                              width: 411,
                              height: 35,
                              child: Container(
                                width: 168,
                                child: TextFormField(
                                  controller:
                                      _model.outroProblemaTextController,
                                  focusNode: _model.outroProblemaFocusNode,
                                  autofocus: false,
                                  obscureText: false,
                                  decoration: InputDecoration(
                                    isDense: true,
                                    labelStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 11,
                                          letterSpacing: 0.2,
                                          fontWeight: FontWeight.bold,
                                          lineHeight: 13,
                                        ),
                                    hintStyle: FlutterFlowTheme.of(context)
                                        .labelMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Color(0xFF153A71),
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                    enabledBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color: Color(0x00000000),
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    errorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    focusedErrorBorder: OutlineInputBorder(
                                      borderSide: BorderSide(
                                        color:
                                            FlutterFlowTheme.of(context).error,
                                        width: 1,
                                      ),
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(11),
                                        bottomRight: Radius.circular(11),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    filled: true,
                                    fillColor: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                  ),
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Inter',
                                        letterSpacing: 0.0,
                                      ),
                                  cursorColor:
                                      FlutterFlowTheme.of(context).primaryText,
                                  validator: _model
                                      .outroProblemaTextControllerValidator
                                      .asValidator(context),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 4, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(40, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          FFAppState().gestante = _model.maeSimValue!;
                          safeSetState(() {});
                          FFAppState().gestanteNao = _model.maeNaoValue!;
                          safeSetState(() {});
                          FFAppState().problemaFigadoRim = _model.figadoRValue!;
                          safeSetState(() {});
                          FFAppState().bomFigadoRim = _model.figadoBValue!;
                          safeSetState(() {});
                          FFAppState().fumante = _model.fumaValue!;
                          safeSetState(() {});
                          FFAppState().fumanteNao = _model.fumaNaoValue!;
                          safeSetState(() {});
                          FFAppState().teveHepatite = _model.titeSimValue!;
                          safeSetState(() {});
                          FFAppState().teveHepatiteNao = _model.titeNaoValue!;
                          safeSetState(() {});
                          FFAppState().diabetes = _model.doceSimValue!;
                          safeSetState(() {});
                          FFAppState().diabetesNao = _model.doceNaoValue!;
                          safeSetState(() {});
                          FFAppState().asma = _model.asmaSimValue!;
                          safeSetState(() {});
                          FFAppState().asmaNao = _model.asmaNaoValue!;
                          safeSetState(() {});
                          FFAppState().problemaCoracao = _model.morreSimValue!;
                          safeSetState(() {});
                          FFAppState().problemaCoracaoNao =
                              _model.morreNaoValue!;
                          safeSetState(() {});
                          FFAppState().problemaRenal = _model.rimSimValue!;
                          safeSetState(() {});
                          FFAppState().problemaRenalNao = _model.rimNaoValue!;
                          safeSetState(() {});
                          FFAppState().outroProblNListado =
                              _model.outroProblemaTextController.text;
                          safeSetState(() {});

                          context.pushNamed('SaudeCadastro2');
                        },
                        text: 'Voltar',
                        options: FFButtonOptions(
                          width: 95,
                          height: 19,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Inter Tight',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(32),
                            bottomRight: Radius.circular(32),
                            topLeft: Radius.circular(32),
                            topRight: Radius.circular(32),
                          ),
                        ),
                      ),
                    ),
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(128, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          FFAppState().gestante = _model.maeSimValue!;
                          safeSetState(() {});
                          FFAppState().gestanteNao = _model.maeNaoValue!;
                          safeSetState(() {});
                          FFAppState().problemaFigadoRim = _model.figadoRValue!;
                          safeSetState(() {});
                          FFAppState().bomFigadoRim = _model.figadoBValue!;
                          safeSetState(() {});
                          FFAppState().fumante = _model.fumaValue!;
                          safeSetState(() {});
                          FFAppState().fumanteNao = _model.fumaNaoValue!;
                          safeSetState(() {});
                          FFAppState().teveHepatite = _model.titeSimValue!;
                          safeSetState(() {});
                          FFAppState().teveHepatiteNao = _model.titeNaoValue!;
                          safeSetState(() {});
                          FFAppState().diabetes = _model.doceSimValue!;
                          safeSetState(() {});
                          FFAppState().diabetesNao = _model.doceNaoValue!;
                          safeSetState(() {});
                          FFAppState().asma = _model.asmaSimValue!;
                          safeSetState(() {});
                          FFAppState().asmaNao = _model.asmaNaoValue!;
                          safeSetState(() {});
                          FFAppState().problemaCoracao = _model.morreSimValue!;
                          safeSetState(() {});
                          FFAppState().problemaCoracaoNao =
                              _model.morreNaoValue!;
                          safeSetState(() {});
                          FFAppState().problemaRenal = _model.rimSimValue!;
                          safeSetState(() {});
                          FFAppState().problemaRenalNao = _model.rimNaoValue!;
                          safeSetState(() {});
                          FFAppState().outroProblNListado =
                              _model.outroProblemaTextController.text;
                          safeSetState(() {});

                          await UsuariosRecord.collection
                              .doc()
                              .set(createUsuariosRecordData(
                                nome: FFAppState().nome,
                                endereco: FFAppState().endereco,
                                numero: FFAppState().numero,
                                complemento: FFAppState().complemento,
                                bairro: FFAppState().bairro,
                                cep: FFAppState().cep,
                                cidade: FFAppState().cidade,
                                uf: FFAppState().uf,
                                telefone: FFAppState().telefone,
                                email: FFAppState().email,
                                dataNascimento: FFAppState().dataNascimento,
                                sexo: FFAppState().sexo,
                                cpf: FFAppState().cpf,
                                senha: FFAppState().senha,
                                confirmaSenha: FFAppState().confirmaSenha,
                                temProblemasSaude: FFAppState().temProblema,
                                descricaoProblema:
                                    FFAppState().descricaoProblema,
                                tomaRemedio: FFAppState().tomaRemedio,
                                qualRemedio: FFAppState().qualRemedio,
                                tomaAnticoncep:
                                    FFAppState().tomaAnticoncepicional,
                                qualAnticoncep:
                                    FFAppState().qualAnticoncepicional,
                                temAlergia: FFAppState().temAlergia,
                                qualAlergia: FFAppState().qualMedAlergia,
                                fezCirurgia: FFAppState().fezCirurgia,
                                qualCirurgia: FFAppState().qualCirurgia,
                                fazTratamento: FFAppState().fazTratamento,
                                qualTratamento: FFAppState().qualTratamento,
                                gestante: FFAppState().gestante,
                                problFigadoRim: FFAppState().problemaFigadoRim,
                                fumante: FFAppState().fumante,
                                teveHepatite: FFAppState().teveHepatite,
                                temDiabetes: FFAppState().diabetes,
                                temAsma: FFAppState().asma,
                                problemaCardiaco: FFAppState().problemaCoracao,
                                problemaRenal: FFAppState().problemaRenal,
                                outroProblNListado:
                                    FFAppState().outroProblNListado,
                                temProblemasSaudeNao:
                                    FFAppState().temProblemaNao,
                                tomaRemedioNao: FFAppState().tomaRemedioNao,
                                tomaAnticoncepNao:
                                    FFAppState().tomaAnticoncepicionalNao,
                                temAlergiaNao: FFAppState().temAlergiaNao,
                                fezCirurgiaNao: FFAppState().fezCirurgiaNao,
                                fazTratamentoNao: FFAppState().fazTratamentoNao,
                                gestanteNao: FFAppState().gestanteNao,
                                bomFigadoRim: FFAppState().bomFigadoRim,
                                fumanteNao: FFAppState().fumanteNao,
                                teveHepatiteNao: FFAppState().teveHepatiteNao,
                                temDiabetesNao: FFAppState().diabetesNao,
                                temAsmaNao: FFAppState().asmaNao,
                                problemaCardiacoNao:
                                    FFAppState().problemaCoracaoNao,
                                problemaRenalNao: FFAppState().problemaRenalNao,
                              ));

                          context.pushNamed('SaudeOla');
                        },
                        text: 'Registrar',
                        options: FFButtonOptions(
                          width: 95,
                          height: 19,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Inter Tight',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(32),
                            bottomRight: Radius.circular(32),
                            topLeft: Radius.circular(32),
                            topRight: Radius.circular(32),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}


# **Saúde Ola**

import '/auth/custom_auth/auth_util.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_ola_model.dart';
export 'saude_ola_model.dart';

class SaudeOlaWidget extends StatefulWidget {
  const SaudeOlaWidget({super.key});

  @override
  State<SaudeOlaWidget> createState() => _SaudeOlaWidgetState();
}

class _SaudeOlaWidgetState extends State<SaudeOlaWidget> {
  late SaudeOlaModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeOlaModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Align(
          alignment: AlignmentDirectional(0, -1),
          child: Padding(
            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
            child: Container(
              width: 462,
              height: 967,
              decoration: BoxDecoration(
                gradient: LinearGradient(
                  colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                  stops: [0, 1],
                  begin: AlignmentDirectional(0, -1),
                  end: AlignmentDirectional(0, 1),
                ),
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(32),
                  bottomRight: Radius.circular(32),
                  topLeft: Radius.circular(32),
                  topRight: Radius.circular(32),
                ),
              ),
              child: Column(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Row(
                    mainAxisSize: MainAxisSize.max,
                    children: [
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 0),
                        child: ClipRRect(
                          borderRadius: BorderRadius.circular(8),
                          child: Image.asset(
                            'assets/images/MaisSaude2.png',
                            width: 70,
                            height: 70,
                            fit: BoxFit.cover,
                          ),
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(15, 70, 0, 0),
                        child: Container(
                          width: 274,
                          height: 28,
                          decoration: BoxDecoration(
                            color: Color(0xFF246536),
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(32),
                              bottomRight: Radius.circular(32),
                              topLeft: Radius.circular(32),
                              topRight: Radius.circular(32),
                            ),
                          ),
                          child: Text(
                            'Olá como posso ajudar?',
                            textAlign: TextAlign.center,
                            style: FlutterFlowTheme.of(context)
                                .bodyMedium
                                .override(
                                  fontFamily: 'Rubik',
                                  color: Colors.white,
                                  fontSize: 21,
                                  letterSpacing: 0.0,
                                  fontWeight: FontWeight.w600,
                                ),
                          ),
                        ),
                      ),
                    ],
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 20, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 28,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        0, 2, 0, 0),
                                    child: Text(
                                      'Agendamento         de Consultas',
                                      textAlign: TextAlign.center,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Colors.white,
                                            fontSize: 10,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 82,
                                  decoration: BoxDecoration(
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(15),
                                      bottomRight: Radius.circular(15),
                                      topLeft: Radius.circular(0),
                                      topRight: Radius.circular(0),
                                    ),
                                  ),
                                  child: InkWell(
                                    splashColor: Colors.transparent,
                                    focusColor: Colors.transparent,
                                    hoverColor: Colors.transparent,
                                    highlightColor: Colors.transparent,
                                    onTap: () async {},
                                    child: Stack(
                                      children: [
                                        Align(
                                          alignment: AlignmentDirectional(0, 0),
                                          child: ClipRRect(
                                            borderRadius:
                                                BorderRadius.circular(8),
                                            child: Image.asset(
                                              'assets/images/Agendamento_consultas.png',
                                              width: 75,
                                              height: 75,
                                              fit: BoxFit.contain,
                                            ),
                                          ),
                                        ),
                                        Opacity(
                                          opacity: 0,
                                          child: Align(
                                            alignment:
                                                AlignmentDirectional(0, 0),
                                            child: FFButtonWidget(
                                              onPressed: () async {
                                                context
                                                    .pushNamed('SaudeConsulta');
                                              },
                                              text: 'Button',
                                              options: FFButtonOptions(
                                                height: 92,
                                                padding: EdgeInsetsDirectional
                                                    .fromSTEB(25, 0, 25, 0),
                                                iconPadding:
                                                    EdgeInsetsDirectional
                                                        .fromSTEB(0, 0, 0, 0),
                                                color:
                                                    FlutterFlowTheme.of(context)
                                                        .primary,
                                                textStyle:
                                                    FlutterFlowTheme.of(context)
                                                        .titleSmall
                                                        .override(
                                                          fontFamily:
                                                              'Inter Tight',
                                                          color: Colors.white,
                                                          letterSpacing: 0.0,
                                                        ),
                                                elevation: 0,
                                                borderRadius:
                                                    BorderRadius.circular(8),
                                              ),
                                            ),
                                          ),
                                        ),
                                      ],
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 97,
                                height: 28,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 2, 0, 0),
                                  child: Text(
                                    'Agendamento        de Exames',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          color: Colors.white,
                                          fontSize: 10,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 97,
                                height: 82,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Stack(
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: ClipRRect(
                                        borderRadius: BorderRadius.circular(8),
                                        child: Image.asset(
                                          'assets/images/calendario_(2).png',
                                          width: 75,
                                          height: 75,
                                          fit: BoxFit.cover,
                                        ),
                                      ),
                                    ),
                                    Opacity(
                                      opacity: 0,
                                      child: Align(
                                        alignment: AlignmentDirectional(0, 0),
                                        child: FFButtonWidget(
                                          onPressed: () async {
                                            context.pushNamed('SaudeAgenda');
                                          },
                                          text: 'Button',
                                          options: FFButtonOptions(
                                            height: 83,
                                            padding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    25, 0, 25, 0),
                                            iconPadding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    0, 0, 0, 0),
                                            color: FlutterFlowTheme.of(context)
                                                .primary,
                                            textStyle:
                                                FlutterFlowTheme.of(context)
                                                    .titleSmall
                                                    .override(
                                                      fontFamily: 'Inter Tight',
                                                      color: Colors.white,
                                                      letterSpacing: 0.0,
                                                    ),
                                            elevation: 0,
                                            borderRadius:
                                                BorderRadius.circular(8),
                                          ),
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 97,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 2, 0, 0),
                                  child: Text(
                                    'Histórico do Paciente',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 10,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 97,
                                height: 81,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Stack(
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: ClipRRect(
                                        borderRadius: BorderRadius.circular(8),
                                        child: Image.asset(
                                          'assets/images/Historico_Paciente.png',
                                          width: 70,
                                          height: 70,
                                          fit: BoxFit.cover,
                                        ),
                                      ),
                                    ),
                                    Opacity(
                                      opacity: 0,
                                      child: Align(
                                        alignment: AlignmentDirectional(0, 0),
                                        child: FFButtonWidget(
                                          onPressed: () async {
                                            context.pushNamed('SaudeHistorico');
                                          },
                                          text: 'Button',
                                          options: FFButtonOptions(
                                            height: 85,
                                            padding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    25, 0, 25, 0),
                                            iconPadding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    0, 0, 0, 0),
                                            color: FlutterFlowTheme.of(context)
                                                .primary,
                                            textStyle:
                                                FlutterFlowTheme.of(context)
                                                    .titleSmall
                                                    .override(
                                                      fontFamily: 'Inter Tight',
                                                      color: Colors.white,
                                                      letterSpacing: 0.0,
                                                    ),
                                            elevation: 0,
                                            borderRadius:
                                                BorderRadius.circular(8),
                                          ),
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                      ],
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 21, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 29,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        0, 2, 0, 0),
                                    child: Text(
                                      'Informações e Dicas de Saúde',
                                      textAlign: TextAlign.center,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Colors.white,
                                            fontSize: 10,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 83,
                                  decoration: BoxDecoration(
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(15),
                                      bottomRight: Radius.circular(15),
                                      topLeft: Radius.circular(0),
                                      topRight: Radius.circular(0),
                                    ),
                                  ),
                                  child: Align(
                                    alignment: AlignmentDirectional(0, 0),
                                    child: Stack(
                                      children: [
                                        Align(
                                          alignment: AlignmentDirectional(0, 0),
                                          child: ClipRRect(
                                            borderRadius:
                                                BorderRadius.circular(8),
                                            child: Image.asset(
                                              'assets/images/dicas_saude.png',
                                              width: 75,
                                              height: 75,
                                              fit: BoxFit.cover,
                                            ),
                                          ),
                                        ),
                                        Opacity(
                                          opacity: 0,
                                          child: Align(
                                            alignment:
                                                AlignmentDirectional(0, 0),
                                            child: FFButtonWidget(
                                              onPressed: () async {
                                                context.pushNamed('SaudeDicas');
                                              },
                                              text: 'Button',
                                              options: FFButtonOptions(
                                                width: 111,
                                                height: 88,
                                                padding: EdgeInsetsDirectional
                                                    .fromSTEB(25, 0, 25, 0),
                                                iconPadding:
                                                    EdgeInsetsDirectional
                                                        .fromSTEB(0, 0, 0, 0),
                                                color:
                                                    FlutterFlowTheme.of(context)
                                                        .primary,
                                                textStyle:
                                                    FlutterFlowTheme.of(context)
                                                        .titleSmall
                                                        .override(
                                                          fontFamily:
                                                              'Inter Tight',
                                                          color: Colors.white,
                                                          letterSpacing: 0.0,
                                                        ),
                                                elevation: 0,
                                                borderRadius:
                                                    BorderRadius.circular(8),
                                              ),
                                            ),
                                          ),
                                        ),
                                      ],
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 97,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 8, 0, 0),
                                  child: Text(
                                    'Ajuda e Suporte',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 11,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 97,
                                height: 83,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Stack(
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: ClipRRect(
                                        borderRadius: BorderRadius.circular(8),
                                        child: Image.asset(
                                          'assets/images/Suporte_4.png',
                                          width: 75,
                                          height: 75,
                                          fit: BoxFit.cover,
                                        ),
                                      ),
                                    ),
                                    Opacity(
                                      opacity: 0,
                                      child: Align(
                                        alignment: AlignmentDirectional(0, 0),
                                        child: FFButtonWidget(
                                          onPressed: () async {
                                            context.pushNamed('SaudeSuporte');
                                          },
                                          text: 'Button',
                                          options: FFButtonOptions(
                                            height: 88,
                                            padding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    25, 0, 25, 0),
                                            iconPadding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    0, 0, 0, 0),
                                            color: FlutterFlowTheme.of(context)
                                                .primary,
                                            textStyle:
                                                FlutterFlowTheme.of(context)
                                                    .titleSmall
                                                    .override(
                                                      fontFamily: 'Inter Tight',
                                                      color: Colors.white,
                                                      letterSpacing: 0.0,
                                                    ),
                                            elevation: 0,
                                            borderRadius:
                                                BorderRadius.circular(8),
                                          ),
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                        Align(
                          alignment: AlignmentDirectional(0, 0),
                          child: Padding(
                            padding:
                                EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                            child: Column(
                              mainAxisSize: MainAxisSize.max,
                              children: [
                                Container(
                                  width: 97,
                                  height: 29,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        0, 8, 0, 0),
                                    child: Text(
                                      'Excluir ou Editar',
                                      textAlign: TextAlign.center,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Colors.white,
                                            fontSize: 11,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                                Container(
                                  width: 97,
                                  height: 83,
                                  decoration: BoxDecoration(
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(15),
                                      bottomRight: Radius.circular(15),
                                      topLeft: Radius.circular(0),
                                      topRight: Radius.circular(0),
                                    ),
                                  ),
                                  child: Stack(
                                    children: [
                                      Align(
                                        alignment: AlignmentDirectional(0, 0),
                                        child: ClipRRect(
                                          borderRadius:
                                              BorderRadius.circular(8),
                                          child: Image.asset(
                                            'assets/images/Group_59.png',
                                            width: 100,
                                            height: 75,
                                            fit: BoxFit.scaleDown,
                                            alignment: Alignment(0, 0),
                                          ),
                                        ),
                                      ),
                                      Opacity(
                                        opacity: 0,
                                        child: Align(
                                          alignment:
                                              AlignmentDirectional(-1.23, 0),
                                          child: FFButtonWidget(
                                            onPressed: () async {
                                              context.pushNamed(
                                                  'SaudeExcluirEditar');
                                            },
                                            text: 'Button',
                                            options: FFButtonOptions(
                                              width: 111,
                                              height: 95,
                                              padding: EdgeInsetsDirectional
                                                  .fromSTEB(16, 0, 16, 0),
                                              iconPadding: EdgeInsetsDirectional
                                                  .fromSTEB(0, 0, 0, 0),
                                              color:
                                                  FlutterFlowTheme.of(context)
                                                      .primary,
                                              textStyle:
                                                  FlutterFlowTheme.of(context)
                                                      .titleSmall
                                                      .override(
                                                        fontFamily:
                                                            'Inter Tight',
                                                        color: Colors.white,
                                                        letterSpacing: 0.0,
                                                      ),
                                              elevation: 0,
                                              borderRadius:
                                                  BorderRadius.circular(8),
                                            ),
                                          ),
                                        ),
                                      ),
                                    ],
                                  ),
                                ),
                              ],
                            ),
                          ),
                        ),
                      ],
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(-1, -1),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(20, 10, 0, 0),
                      child: Row(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Align(
                            alignment: AlignmentDirectional(0, 0),
                            child: Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                              child: FFButtonWidget(
                                onPressed: () async {
                                  GoRouter.of(context).prepareAuthEvent();
                                  await authManager.signOut();
                                  GoRouter.of(context).clearRedirectLocation();

                                  context.pushNamedAuth(
                                      'SaudeLogin', context.mounted);
                                },
                                text: 'Sair do aplicativo',
                                options: FFButtonOptions(
                                  width: 356,
                                  height: 31,
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      3, 0, 0, 0),
                                  iconPadding: EdgeInsetsDirectional.fromSTEB(
                                      0, 0, 0, 0),
                                  color: Color(0xFF246536),
                                  textStyle: FlutterFlowTheme.of(context)
                                      .titleSmall
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 21,
                                        letterSpacing: 0.0,
                                      ),
                                  elevation: 0,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(20),
                                    bottomRight: Radius.circular(20),
                                    topLeft: Radius.circular(20),
                                    topRight: Radius.circular(20),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}


# **Agendamento Consulta**

import '/backend/backend.dart';
import '/flutter_flow/flutter_flow_calendar.dart';
import '/flutter_flow/flutter_flow_drop_down.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import '/flutter_flow/form_field_controller.dart';
import 'package:cloud_firestore/cloud_firestore.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_consulta_model.dart';
export 'saude_consulta_model.dart';

class SaudeConsultaWidget extends StatefulWidget {
  const SaudeConsultaWidget({super.key});

  @override
  State<SaudeConsultaWidget> createState() => _SaudeConsultaWidgetState();
}

class _SaudeConsultaWidgetState extends State<SaudeConsultaWidget> {
  late SaudeConsultaModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeConsultaModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Container(
          width: MediaQuery.sizeOf(context).width,
          height: MediaQuery.sizeOf(context).height * 1,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
              stops: [0, 1],
              begin: AlignmentDirectional(0, -1),
              end: AlignmentDirectional(0, 1),
            ),
            borderRadius: BorderRadius.only(
              bottomLeft: Radius.circular(32),
              bottomRight: Radius.circular(32),
              topLeft: Radius.circular(32),
              topRight: Radius.circular(32),
            ),
          ),
          child: Column(
            mainAxisSize: MainAxisSize.max,
            children: [
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 25, 0, 25),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(5, 20, 0, 0),
                      child: ClipRRect(
                        borderRadius: BorderRadius.circular(8),
                        child: Image.asset(
                          'assets/images/MaisSaude2.png',
                          width: 70,
                          height: 70,
                          fit: BoxFit.cover,
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(10, 20, 0, 0),
                        child: Container(
                          width: 278,
                          height: 28,
                          decoration: BoxDecoration(
                            color: Color(0xFF246536),
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(20),
                              bottomRight: Radius.circular(20),
                              topLeft: Radius.circular(20),
                              topRight: Radius.circular(20),
                            ),
                          ),
                          child: Align(
                            alignment: AlignmentDirectional(0, 0),
                            child: Text(
                              'AGENDAMENTO DE CONSULTAS',
                              textAlign: TextAlign.center,
                              style: FlutterFlowTheme.of(context)
                                  .bodyMedium
                                  .override(
                                    fontFamily: 'Rubik',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                    fontWeight: FontWeight.w600,
                                  ),
                            ),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Container(
                    width: MediaQuery.sizeOf(context).width,
                    height: 68,
                    decoration: BoxDecoration(),
                    child: Column(
                      mainAxisSize: MainAxisSize.max,
                      mainAxisAlignment: MainAxisAlignment.start,
                      children: [
                        Align(
                          alignment: AlignmentDirectional(0, 0),
                          child: Container(
                            width: 380,
                            height: 20,
                            decoration: BoxDecoration(
                              color: Color(0xFF153A71),
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(0),
                                bottomRight: Radius.circular(0),
                                topLeft: Radius.circular(17),
                                topRight: Radius.circular(17),
                              ),
                            ),
                            child: Align(
                              alignment: AlignmentDirectional(-1, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Text(
                                  'Escolha a especialidade',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                          ),
                        ),
                        Container(
                          width: 378,
                          height: 40,
                          decoration: BoxDecoration(
                            color: FlutterFlowTheme.of(context)
                                .secondaryBackground,
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(17),
                              bottomRight: Radius.circular(17),
                              topLeft: Radius.circular(0),
                              topRight: Radius.circular(0),
                            ),
                          ),
                          child: FlutterFlowDropDown<String>(
                            controller: _model.dropDownValueController1 ??=
                                FormFieldController<String>(
                              _model.dropDownValue1 ??= '',
                            ),
                            options: List<String>.from([
                              'Oftalmologista',
                              'Ortopedista',
                              'Pneulmogista',
                              'Cardiologista',
                              'Traumatologista',
                              'Dermatologista'
                            ]),
                            optionLabels: [
                              'Oftalmologista',
                              'Ortopedista',
                              'Pneulmogista',
                              'Cardiologista',
                              'Traumatologista',
                              'Dermatologista'
                            ],
                            onChanged: (val) =>
                                safeSetState(() => _model.dropDownValue1 = val),
                            width: 270,
                            height: 40,
                            textStyle: FlutterFlowTheme.of(context)
                                .bodyMedium
                                .override(
                                  fontFamily: 'Inter',
                                  letterSpacing: 0.0,
                                ),
                            icon: Icon(
                              Icons.arrow_drop_down_circle_outlined,
                              color: Color(0xFF246536),
                              size: 24,
                            ),
                            fillColor: FlutterFlowTheme.of(context)
                                .secondaryBackground,
                            elevation: 2,
                            borderColor: Colors.transparent,
                            borderWidth: 0,
                            borderRadius: 12,
                            margin:
                                EdgeInsetsDirectional.fromSTEB(12, 0, 12, 0),
                            hidesUnderline: true,
                            isOverButton: false,
                            isSearchable: false,
                            isMultiSelect: false,
                          ),
                        ),
                      ],
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Container(
                    width: MediaQuery.sizeOf(context).width,
                    height: 68,
                    decoration: BoxDecoration(
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(0),
                        bottomRight: Radius.circular(0),
                        topLeft: Radius.circular(0),
                        topRight: Radius.circular(0),
                      ),
                    ),
                    child: Column(
                      mainAxisSize: MainAxisSize.max,
                      mainAxisAlignment: MainAxisAlignment.start,
                      children: [
                        Align(
                          alignment: AlignmentDirectional(0, 0),
                          child: Container(
                            width: 380,
                            height: 20,
                            decoration: BoxDecoration(
                              color: Color(0xFF153A71),
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(0),
                                bottomRight: Radius.circular(0),
                                topLeft: Radius.circular(17),
                                topRight: Radius.circular(17),
                              ),
                            ),
                            child: Align(
                              alignment: AlignmentDirectional(-1, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Text(
                                  'Escolha a unidade',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                          ),
                        ),
                        Container(
                          width: 378,
                          height: 40,
                          decoration: BoxDecoration(
                            color: FlutterFlowTheme.of(context)
                                .secondaryBackground,
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(17),
                              bottomRight: Radius.circular(17),
                              topLeft: Radius.circular(0),
                              topRight: Radius.circular(0),
                            ),
                          ),
                          child: FlutterFlowDropDown<String>(
                            controller: _model.dropDownValueController2 ??=
                                FormFieldController<String>(
                              _model.dropDownValue2 ??= '',
                            ),
                            options: List<String>.from(
                                ['Hospital Geral', 'Clinica +Saúde']),
                            optionLabels: ['Hospital Geral', 'Clinica +Saúde'],
                            onChanged: (val) =>
                                safeSetState(() => _model.dropDownValue2 = val),
                            width: 270,
                            height: 40,
                            textStyle: FlutterFlowTheme.of(context)
                                .bodyMedium
                                .override(
                                  fontFamily: 'Inter',
                                  letterSpacing: 0.0,
                                ),
                            icon: Icon(
                              Icons.arrow_drop_down_circle_outlined,
                              color: Color(0xFF246536),
                              size: 24,
                            ),
                            fillColor: FlutterFlowTheme.of(context)
                                .secondaryBackground,
                            elevation: 2,
                            borderColor: Colors.transparent,
                            borderWidth: 0,
                            borderRadius: 12,
                            margin:
                                EdgeInsetsDirectional.fromSTEB(12, 0, 12, 0),
                            hidesUnderline: true,
                            isOverButton: false,
                            isSearchable: false,
                            isMultiSelect: false,
                          ),
                        ),
                      ],
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(5, 0, 0, 0),
                    child: Container(
                      width: 380,
                      height: 284,
                      decoration: BoxDecoration(
                        borderRadius: BorderRadius.only(
                          bottomLeft: Radius.circular(17),
                          bottomRight: Radius.circular(17),
                          topLeft: Radius.circular(17),
                          topRight: Radius.circular(17),
                        ),
                      ),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Container(
                            width: 380,
                            height: 20,
                            decoration: BoxDecoration(
                              color: Color(0xFF153A71),
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(0),
                                bottomRight: Radius.circular(0),
                                topLeft: Radius.circular(17),
                                topRight: Radius.circular(17),
                              ),
                            ),
                            child: Align(
                              alignment: AlignmentDirectional(-1, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Text(
                                  'Datas disponiveis',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                          ),
                          Container(
                            width: 390,
                            height: 256,
                            decoration: BoxDecoration(
                              color: FlutterFlowTheme.of(context)
                                  .secondaryBackground,
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(17),
                                bottomRight: Radius.circular(17),
                                topLeft: Radius.circular(0),
                                topRight: Radius.circular(0),
                              ),
                            ),
                            child: FlutterFlowCalendar(
                              color: Color(0xFF246536),
                              iconColor:
                                  FlutterFlowTheme.of(context).secondaryText,
                              weekFormat: false,
                              weekStartsMonday: false,
                              rowHeight: 30,
                              onChange: (DateTimeRange? newSelectedDate) {
                                safeSetState(() => _model.calendarSelectedDay =
                                    newSelectedDate);
                              },
                              titleStyle: FlutterFlowTheme.of(context)
                                  .titleLarge
                                  .override(
                                    fontFamily: 'Inter Tight',
                                    letterSpacing: 0.0,
                                  ),
                              dayOfWeekStyle: FlutterFlowTheme.of(context)
                                  .bodyLarge
                                  .override(
                                    fontFamily: 'Inter',
                                    letterSpacing: 0.0,
                                  ),
                              dateStyle: FlutterFlowTheme.of(context)
                                  .bodyMedium
                                  .override(
                                    fontFamily: 'Inter',
                                    fontSize: 14,
                                    letterSpacing: 0.0,
                                  ),
                              selectedDateStyle: FlutterFlowTheme.of(context)
                                  .titleSmall
                                  .override(
                                    fontFamily: 'Inter Tight',
                                    fontSize: 16,
                                    letterSpacing: 0.0,
                                    fontWeight: FontWeight.w500,
                                  ),
                              inactiveDateStyle: FlutterFlowTheme.of(context)
                                  .labelMedium
                                  .override(
                                    fontFamily: 'Inter',
                                    fontSize: 14,
                                    letterSpacing: 0.0,
                                  ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Container(
                    width: 390,
                    height: 65,
                    decoration: BoxDecoration(
                      borderRadius: BorderRadius.only(
                        bottomLeft: Radius.circular(17),
                        bottomRight: Radius.circular(17),
                        topLeft: Radius.circular(17),
                        topRight: Radius.circular(17),
                      ),
                    ),
                    child: Column(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Container(
                          width: 379,
                          height: 20,
                          decoration: BoxDecoration(
                            color: Color(0xFF153A71),
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(0),
                              bottomRight: Radius.circular(0),
                              topLeft: Radius.circular(17),
                              topRight: Radius.circular(17),
                            ),
                          ),
                          child: Align(
                            alignment: AlignmentDirectional(-1, 0),
                            child: Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                              child: Text(
                                'Hora da consulta',
                                style: FlutterFlowTheme.of(context)
                                    .bodyMedium
                                    .override(
                                      fontFamily: 'Rubik',
                                      color: Colors.white,
                                      letterSpacing: 0.0,
                                      fontWeight: FontWeight.w600,
                                    ),
                              ),
                            ),
                          ),
                        ),
                        Container(
                          width: 378,
                          height: 40,
                          decoration: BoxDecoration(
                            color: FlutterFlowTheme.of(context)
                                .secondaryBackground,
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(17),
                              bottomRight: Radius.circular(17),
                              topLeft: Radius.circular(0),
                              topRight: Radius.circular(0),
                            ),
                          ),
                          child: FlutterFlowDropDown<String>(
                            controller: _model.dropDownValueController3 ??=
                                FormFieldController<String>(
                              _model.dropDownValue3 ??= '',
                            ),
                            options: List<String>.from([
                              '8:00',
                              '8:30',
                              '9:00',
                              '9:30',
                              '10:00',
                              '10:30',
                              '11:00',
                              '11:30',
                              '12:00',
                              '12:30',
                              '13:00',
                              '13:30',
                              '14:00',
                              '14:30',
                              '15:00',
                              '15:30',
                              '16:00',
                              '16:30',
                              '17:00',
                              '17:30',
                              '18:00',
                              '18:30',
                              '19:00',
                              '19:30',
                              '20:00',
                              '20:30',
                              '21:00',
                              '21:30',
                              '22:00'
                            ]),
                            optionLabels: [
                              '8:00',
                              '8:30',
                              '9:00',
                              '9:30',
                              '10:00',
                              '10:30',
                              '11:00',
                              '11:30',
                              '12:00',
                              '12:30',
                              '13:00',
                              '13:30',
                              '14:00',
                              '14:30',
                              '15:00',
                              '15:30',
                              '16:00',
                              '16:30',
                              '17:00',
                              '17:30',
                              '18:00',
                              '18:30',
                              '19:00',
                              '19:30',
                              '20:00',
                              '20:30',
                              '21:00',
                              '21:30',
                              '22:00'
                            ],
                            onChanged: (val) =>
                                safeSetState(() => _model.dropDownValue3 = val),
                            width: 200,
                            height: 40,
                            textStyle: FlutterFlowTheme.of(context)
                                .bodyMedium
                                .override(
                                  fontFamily: 'Rubik',
                                  letterSpacing: 0.0,
                                ),
                            icon: Icon(
                              Icons.arrow_drop_down_circle_outlined,
                              color: Color(0xFF246536),
                              size: 24,
                            ),
                            fillColor: Colors.white,
                            elevation: 2,
                            borderColor: Colors.transparent,
                            borderWidth: 0,
                            borderRadius: 12,
                            margin:
                                EdgeInsetsDirectional.fromSTEB(12, 0, 12, 0),
                            hidesUnderline: true,
                            isOverButton: false,
                            isSearchable: false,
                            isMultiSelect: false,
                          ),
                        ),
                      ],
                    ),
                  ),
                ],
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 40, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(20, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          context.pushNamed('SaudeOla');
                        },
                        text: 'Voltar',
                        options: FFButtonOptions(
                          width: 102,
                          height: 25,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Rubik',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(20),
                            bottomRight: Radius.circular(20),
                            topLeft: Radius.circular(20),
                            topRight: Radius.circular(20),
                          ),
                        ),
                      ),
                    ),
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(140, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          await UsuariosRecord.collection
                              .doc()
                              .set(createUsuariosRecordData(
                                especialidade: _model.dropDownValue1,
                                unidade: _model.dropDownValue2,
                                datas: _model.calendarSelectedDay?.start,
                                hora: _model.dropDownValue3,
                              ));

                          context.pushNamed('SaudeConsultaAgenSucesso');
                        },
                        text: 'Agendar',
                        options: FFButtonOptions(
                          height: 25,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Rubik',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(20),
                            bottomRight: Radius.circular(20),
                            topLeft: Radius.circular(20),
                            topRight: Radius.circular(20),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ].divide(SizedBox(height: 12)),
          ),
        ),
      ),
    );
  }
}


# **Agendamento Consulta Sucesso**

import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_consulta_agen_sucesso_model.dart';
export 'saude_consulta_agen_sucesso_model.dart';

class SaudeConsultaAgenSucessoWidget extends StatefulWidget {
  const SaudeConsultaAgenSucessoWidget({super.key});

  @override
  State<SaudeConsultaAgenSucessoWidget> createState() =>
      _SaudeConsultaAgenSucessoWidgetState();
}

class _SaudeConsultaAgenSucessoWidgetState
    extends State<SaudeConsultaAgenSucessoWidget> {
  late SaudeConsultaAgenSucessoModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeConsultaAgenSucessoModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Container(
          width: MediaQuery.sizeOf(context).width,
          height: MediaQuery.sizeOf(context).height * 1,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
              stops: [0, 1],
              begin: AlignmentDirectional(0, -1),
              end: AlignmentDirectional(0, 1),
            ),
            borderRadius: BorderRadius.only(
              bottomLeft: Radius.circular(32),
              bottomRight: Radius.circular(32),
              topLeft: Radius.circular(32),
              topRight: Radius.circular(32),
            ),
          ),
          child: Column(
            mainAxisSize: MainAxisSize.max,
            children: [
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 70, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(5, 20, 0, 0),
                      child: ClipRRect(
                        borderRadius: BorderRadius.circular(8),
                        child: Image.asset(
                          'assets/images/MaisSaude2.png',
                          width: 70,
                          height: 70,
                          fit: BoxFit.cover,
                        ),
                      ),
                    ),
                    Align(
                      alignment: AlignmentDirectional(0, 0),
                      child: Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(10, 20, 0, 0),
                        child: Container(
                          width: 278,
                          height: 28,
                          decoration: BoxDecoration(
                            color: Color(0xFF246536),
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(20),
                              bottomRight: Radius.circular(20),
                              topLeft: Radius.circular(20),
                              topRight: Radius.circular(20),
                            ),
                          ),
                          child: Align(
                            alignment: AlignmentDirectional(0, 0),
                            child: Text(
                              'AGENDAMENTO DE CONSULTAS',
                              textAlign: TextAlign.center,
                              style: FlutterFlowTheme.of(context)
                                  .bodyMedium
                                  .override(
                                    fontFamily: 'Rubik',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                    fontWeight: FontWeight.w600,
                                  ),
                            ),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 100, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Column(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                          child: Container(
                            width: 369,
                            height: 15,
                            decoration: BoxDecoration(
                              color: Color(0xFF153A71),
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(0),
                                bottomRight: Radius.circular(0),
                                topLeft: Radius.circular(12),
                                topRight: Radius.circular(12),
                              ),
                            ),
                          ),
                        ),
                        Align(
                          alignment: AlignmentDirectional(0, 0),
                          child: Padding(
                            padding:
                                EdgeInsetsDirectional.fromSTEB(12, 0, 0, 0),
                            child: Container(
                              width: 368,
                              height: 200,
                              decoration: BoxDecoration(
                                color: FlutterFlowTheme.of(context)
                                    .secondaryBackground,
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(17),
                                  bottomRight: Radius.circular(17),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(0, 0),
                                child: Text(
                                  'Agendamento da consulta realizado com sucesso!',
                                  textAlign: TextAlign.center,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Color(0xFF153A71),
                                        fontSize: 26,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w600,
                                      ),
                                ),
                              ),
                            ),
                          ),
                        ),
                      ],
                    ),
                  ],
                ),
              ),
              Padding(
                padding: EdgeInsetsDirectional.fromSTEB(0, 100, 0, 0),
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(165, 0, 0, 0),
                      child: FFButtonWidget(
                        onPressed: () async {
                          context.pushNamed('SaudeOla');
                        },
                        text: 'Voltar',
                        options: FFButtonOptions(
                          height: 22,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Rubik',
                                    color: Colors.white,
                                    letterSpacing: 0.0,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(20),
                            bottomRight: Radius.circular(20),
                            topLeft: Radius.circular(20),
                            topRight: Radius.circular(20),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
}


# **Agendamento Exames**

import '/backend/backend.dart';
import '/flutter_flow/flutter_flow_calendar.dart';
import '/flutter_flow/flutter_flow_drop_down.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import '/flutter_flow/form_field_controller.dart';
import 'package:cloud_firestore/cloud_firestore.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_agenda_model.dart';
export 'saude_agenda_model.dart';

class SaudeAgendaWidget extends StatefulWidget {
  const SaudeAgendaWidget({super.key});

  @override
  State<SaudeAgendaWidget> createState() => _SaudeAgendaWidgetState();
}

class _SaudeAgendaWidgetState extends State<SaudeAgendaWidget> {
  late SaudeAgendaModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeAgendaModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Align(
          alignment: AlignmentDirectional(0, -1),
          child: Padding(
            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
            child: Container(
              width: 392,
              height: 967,
              decoration: BoxDecoration(
                gradient: LinearGradient(
                  colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                  stops: [0, 1],
                  begin: AlignmentDirectional(0, -1),
                  end: AlignmentDirectional(0, 1),
                ),
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(32),
                  bottomRight: Radius.circular(32),
                  topLeft: Radius.circular(32),
                  topRight: Radius.circular(32),
                ),
                shape: BoxShape.rectangle,
              ),
              alignment: AlignmentDirectional(0, 0),
              child: Align(
                alignment: AlignmentDirectional(0, -1),
                child: Padding(
                  padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
                  child: Column(
                    mainAxisSize: MainAxisSize.max,
                    children: [
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 65, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Align(
                              alignment: AlignmentDirectional(-1, -1),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                                child: ClipRRect(
                                  borderRadius: BorderRadius.circular(8),
                                  child: Image.asset(
                                    'assets/images/saude-removebg-preview.png',
                                    width: 70,
                                    height: 70,
                                    fit: BoxFit.fill,
                                    alignment: Alignment(-1, -1),
                                  ),
                                ),
                              ),
                            ),
                            Align(
                              alignment: AlignmentDirectional(-1, -1),
                              child: Container(
                                width: 271,
                                height: 25,
                                decoration: BoxDecoration(
                                  color: Color(0xFF246536),
                                  borderRadius: BorderRadius.circular(24),
                                  shape: BoxShape.rectangle,
                                ),
                                alignment: AlignmentDirectional(0, -1),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Text(
                                    'AGENDAMENTO DE EXAMES',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color:
                                              FlutterFlowTheme.of(context).info,
                                          fontSize: 15,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 10, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                              child: Container(
                                width: 375,
                                height: 63,
                                decoration: BoxDecoration(
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(17),
                                    bottomRight: Radius.circular(17),
                                    topLeft: Radius.circular(17),
                                    topRight: Radius.circular(17),
                                  ),
                                ),
                                child: Column(
                                  mainAxisSize: MainAxisSize.max,
                                  children: [
                                    Column(
                                      mainAxisSize: MainAxisSize.max,
                                      children: [
                                        Container(
                                          width: 407,
                                          height: 23,
                                          decoration: BoxDecoration(
                                            color: Color(0xFF153A71),
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(0),
                                              bottomRight: Radius.circular(0),
                                              topLeft: Radius.circular(17),
                                              topRight: Radius.circular(17),
                                            ),
                                          ),
                                          child: Align(
                                            alignment:
                                                AlignmentDirectional(-1, 0),
                                            child: Padding(
                                              padding: EdgeInsetsDirectional
                                                  .fromSTEB(15, 0, 0, 0),
                                              child: Text(
                                                'Escolha o tipo de exame',
                                                textAlign: TextAlign.start,
                                                style:
                                                    FlutterFlowTheme.of(context)
                                                        .bodyMedium
                                                        .override(
                                                          fontFamily: 'Rubik',
                                                          color: FlutterFlowTheme
                                                                  .of(context)
                                                              .secondaryBackground,
                                                          fontSize: 16,
                                                          letterSpacing: 0.0,
                                                          fontWeight:
                                                              FontWeight.w600,
                                                        ),
                                              ),
                                            ),
                                          ),
                                        ),
                                      ],
                                    ),
                                    Container(
                                      width: 377,
                                      height: 38,
                                      decoration: BoxDecoration(
                                        color: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      child: FlutterFlowDropDown<String>(
                                        controller:
                                            _model.dropDownValueController1 ??=
                                                FormFieldController<String>(
                                          _model.dropDownValue1 ??= '',
                                        ),
                                        options: List<String>.from([
                                          'Colesterol total e triglicerídeos',
                                          'Creatinina',
                                          'Densitometria óssea',
                                          'Eletrocardiograma',
                                          'Exame de urina',
                                          'Hemograma',
                                          'Mamografia',
                                          'PCR',
                                          'Raio-X',
                                          'Ressonância Magnética',
                                          'USG Abdome Total',
                                          'USG Pélvica',
                                          'USG Obstétrica'
                                        ]),
                                        optionLabels: [
                                          'Colesterol total e triglicerídeos',
                                          'Creatinina',
                                          'Densitometria óssea',
                                          'Eletrocardiograma',
                                          'Exame de urina',
                                          'Hemograma',
                                          'Mamografia',
                                          'PCR',
                                          'Raio-X',
                                          'Ressonância Magnética',
                                          'USG Abdome Total',
                                          'USG Pélvica',
                                          'USG Obstétrica'
                                        ],
                                        onChanged: (val) => safeSetState(
                                            () => _model.dropDownValue1 = val),
                                        width: 338,
                                        height: 40,
                                        textStyle: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                        icon: Icon(
                                          Icons.arrow_drop_down_circle_outlined,
                                          color: Color(0xFF246536),
                                          size: 24,
                                        ),
                                        fillColor: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        elevation: 2,
                                        borderColor: Colors.transparent,
                                        borderWidth: 0,
                                        borderRadius: 8,
                                        margin: EdgeInsetsDirectional.fromSTEB(
                                            12, 0, 12, 0),
                                        hidesUnderline: true,
                                        isOverButton: false,
                                        isSearchable: false,
                                        isMultiSelect: false,
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 20, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                              child: Container(
                                width: 375,
                                height: 64,
                                decoration: BoxDecoration(
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(17),
                                    bottomRight: Radius.circular(17),
                                    topLeft: Radius.circular(17),
                                    topRight: Radius.circular(17),
                                  ),
                                ),
                                child: Column(
                                  mainAxisSize: MainAxisSize.max,
                                  children: [
                                    Column(
                                      mainAxisSize: MainAxisSize.max,
                                      children: [
                                        Container(
                                          width: 407,
                                          height: 23,
                                          decoration: BoxDecoration(
                                            color: Color(0xFF153A71),
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(0),
                                              bottomRight: Radius.circular(0),
                                              topLeft: Radius.circular(17),
                                              topRight: Radius.circular(17),
                                            ),
                                          ),
                                          child: Align(
                                            alignment:
                                                AlignmentDirectional(-1, 0),
                                            child: Padding(
                                              padding: EdgeInsetsDirectional
                                                  .fromSTEB(15, 0, 0, 0),
                                              child: Text(
                                                'Escolha a Unidade',
                                                textAlign: TextAlign.start,
                                                style:
                                                    FlutterFlowTheme.of(context)
                                                        .bodyMedium
                                                        .override(
                                                          fontFamily: 'Rubik',
                                                          color: FlutterFlowTheme
                                                                  .of(context)
                                                              .secondaryBackground,
                                                          fontSize: 16,
                                                          letterSpacing: 0.0,
                                                          fontWeight:
                                                              FontWeight.w600,
                                                        ),
                                              ),
                                            ),
                                          ),
                                        ),
                                      ],
                                    ),
                                    Container(
                                      width: 377,
                                      height: 38,
                                      decoration: BoxDecoration(
                                        color: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      child: FlutterFlowDropDown<String>(
                                        controller:
                                            _model.dropDownValueController2 ??=
                                                FormFieldController<String>(
                                          _model.dropDownValue2 ??= '',
                                        ),
                                        options: List<String>.from([
                                          'Laboratório Centro',
                                          'Laboratório Leste',
                                          'Laboratório Norte',
                                          'Laboratório Oeste',
                                          'Laboratório Sul'
                                        ]),
                                        optionLabels: [
                                          'Laboratório Centro',
                                          'Laboratório Leste',
                                          'Laboratório Norte',
                                          'Laboratório Oeste',
                                          'Laboratório Sul'
                                        ],
                                        onChanged: (val) => safeSetState(
                                            () => _model.dropDownValue2 = val),
                                        width: 338,
                                        height: 40,
                                        textStyle: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                        icon: Icon(
                                          Icons.arrow_drop_down_circle_outlined,
                                          color: Color(0xFF246536),
                                          size: 24,
                                        ),
                                        fillColor: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        elevation: 2,
                                        borderColor: Colors.transparent,
                                        borderWidth: 0,
                                        borderRadius: 8,
                                        margin: EdgeInsetsDirectional.fromSTEB(
                                            12, 0, 12, 0),
                                        hidesUnderline: true,
                                        isOverButton: false,
                                        isSearchable: false,
                                        isMultiSelect: false,
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                              child: Container(
                                width: 372,
                                height: 290,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(17),
                                    bottomRight: Radius.circular(17),
                                    topLeft: Radius.circular(17),
                                    topRight: Radius.circular(17),
                                  ),
                                ),
                                child: Column(
                                  mainAxisSize: MainAxisSize.max,
                                  children: [
                                    Container(
                                      width: 379,
                                      height: 20,
                                      decoration: BoxDecoration(
                                        color: Color(0xFF153A71),
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(0),
                                          bottomRight: Radius.circular(0),
                                          topLeft: Radius.circular(17),
                                          topRight: Radius.circular(17),
                                        ),
                                      ),
                                      child: Align(
                                        alignment: AlignmentDirectional(-1, -1),
                                        child: Padding(
                                          padding:
                                              EdgeInsetsDirectional.fromSTEB(
                                                  20, 0, 0, 0),
                                          child: Text(
                                            'Datas Disponíveis',
                                            style: FlutterFlowTheme.of(context)
                                                .bodyMedium
                                                .override(
                                                  fontFamily: 'Rubik',
                                                  color: FlutterFlowTheme.of(
                                                          context)
                                                      .secondaryBackground,
                                                  fontSize: 16,
                                                  letterSpacing: 0.0,
                                                  fontWeight: FontWeight.w600,
                                                ),
                                          ),
                                        ),
                                      ),
                                    ),
                                    Container(
                                      width: 367,
                                      height: 242,
                                      decoration: BoxDecoration(
                                        color: FlutterFlowTheme.of(context)
                                            .secondaryBackground,
                                        borderRadius: BorderRadius.only(
                                          bottomLeft: Radius.circular(17),
                                          bottomRight: Radius.circular(17),
                                          topLeft: Radius.circular(0),
                                          topRight: Radius.circular(0),
                                        ),
                                      ),
                                      child: FlutterFlowCalendar(
                                        color: Color(0xFF246536),
                                        iconColor: FlutterFlowTheme.of(context)
                                            .secondaryText,
                                        weekFormat: false,
                                        weekStartsMonday: false,
                                        rowHeight: 30,
                                        onChange:
                                            (DateTimeRange? newSelectedDate) {
                                          safeSetState(() =>
                                              _model.calendarSelectedDay =
                                                  newSelectedDate);
                                        },
                                        titleStyle: FlutterFlowTheme.of(context)
                                            .titleLarge
                                            .override(
                                              fontFamily: 'Rubik',
                                              fontSize: 16,
                                              letterSpacing: 0.0,
                                            ),
                                        dayOfWeekStyle:
                                            FlutterFlowTheme.of(context)
                                                .bodyLarge
                                                .override(
                                                  fontFamily: 'Inter',
                                                  letterSpacing: 0.0,
                                                  fontWeight: FontWeight.w600,
                                                ),
                                        dateStyle: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Inter',
                                              fontSize: 16,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                        selectedDateStyle:
                                            FlutterFlowTheme.of(context)
                                                .titleSmall
                                                .override(
                                                  fontFamily: 'Inter Tight',
                                                  letterSpacing: 0.0,
                                                ),
                                        inactiveDateStyle:
                                            FlutterFlowTheme.of(context)
                                                .labelMedium
                                                .override(
                                                  fontFamily: 'Inter',
                                                  letterSpacing: 0.0,
                                                ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 15, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                              child: Container(
                                width: 375,
                                height: 64,
                                decoration: BoxDecoration(
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(17),
                                    bottomRight: Radius.circular(17),
                                    topLeft: Radius.circular(17),
                                    topRight: Radius.circular(17),
                                  ),
                                ),
                                child: Column(
                                  mainAxisSize: MainAxisSize.max,
                                  children: [
                                    Column(
                                      mainAxisSize: MainAxisSize.max,
                                      children: [
                                        Container(
                                          width: 407,
                                          height: 23,
                                          decoration: BoxDecoration(
                                            color: Color(0xFF153A71),
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(0),
                                              bottomRight: Radius.circular(0),
                                              topLeft: Radius.circular(17),
                                              topRight: Radius.circular(17),
                                            ),
                                          ),
                                          child: Align(
                                            alignment:
                                                AlignmentDirectional(-1, 0),
                                            child: Padding(
                                              padding: EdgeInsetsDirectional
                                                  .fromSTEB(15, 0, 0, 0),
                                              child: Text(
                                                'Hora do Exame',
                                                textAlign: TextAlign.start,
                                                style:
                                                    FlutterFlowTheme.of(context)
                                                        .bodyMedium
                                                        .override(
                                                          fontFamily: 'Rubik',
                                                          color: FlutterFlowTheme
                                                                  .of(context)
                                                              .secondaryBackground,
                                                          fontSize: 16,
                                                          letterSpacing: 0.0,
                                                          fontWeight:
                                                              FontWeight.w600,
                                                        ),
                                              ),
                                            ),
                                          ),
                                        ),
                                        Container(
                                          width: 377,
                                          height: 40,
                                          decoration: BoxDecoration(
                                            color: FlutterFlowTheme.of(context)
                                                .secondaryBackground,
                                            borderRadius: BorderRadius.only(
                                              bottomLeft: Radius.circular(17),
                                              bottomRight: Radius.circular(17),
                                              topLeft: Radius.circular(0),
                                              topRight: Radius.circular(0),
                                            ),
                                          ),
                                          child: FlutterFlowDropDown<String>(
                                            controller: _model
                                                    .dropDownValueController3 ??=
                                                FormFieldController<String>(
                                              _model.dropDownValue3 ??= '',
                                            ),
                                            options: List<String>.from([
                                              'Option 1',
                                              'Option 2',
                                              'Option 3',
                                              '3',
                                              '4',
                                              '5',
                                              '6',
                                              '7',
                                              '8',
                                              '9',
                                              '10',
                                              '11',
                                              '12',
                                              '13',
                                              '14',
                                              '15',
                                              '16',
                                              '17',
                                              '18',
                                              '19',
                                              '20'
                                            ]),
                                            optionLabels: [
                                              '06:00',
                                              '06:30',
                                              '07:10',
                                              '07:30',
                                              '08:00',
                                              '08:30',
                                              '09:15',
                                              '09:30',
                                              '10:00',
                                              '10:30',
                                              '11:00',
                                              '11:30',
                                              '12:00',
                                              '13:00',
                                              '14:20',
                                              '15:00',
                                              '16:10',
                                              '16:30',
                                              '17:00',
                                              '17:30',
                                              '18:00'
                                            ],
                                            onChanged: (val) => safeSetState(
                                                () => _model.dropDownValue3 =
                                                    val),
                                            width: 338,
                                            height: 40,
                                            textStyle:
                                                FlutterFlowTheme.of(context)
                                                    .bodyMedium
                                                    .override(
                                                      fontFamily: 'Rubik',
                                                      letterSpacing: 0.0,
                                                      fontWeight:
                                                          FontWeight.w600,
                                                    ),
                                            icon: Icon(
                                              Icons
                                                  .arrow_drop_down_circle_outlined,
                                              color: Color(0xFF246536),
                                              size: 24,
                                            ),
                                            fillColor:
                                                FlutterFlowTheme.of(context)
                                                    .secondaryBackground,
                                            elevation: 2,
                                            borderColor: Colors.transparent,
                                            borderWidth: 0,
                                            borderRadius: 8,
                                            margin:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    12, 0, 12, 0),
                                            hidesUnderline: true,
                                            isOverButton: false,
                                            isSearchable: false,
                                            isMultiSelect: false,
                                          ),
                                        ),
                                      ],
                                    ),
                                  ],
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 15, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(20, 0, 0, 0),
                              child: FFButtonWidget(
                                onPressed: () async {
                                  context.pushNamed('SaudeOla');
                                },
                                text: 'Voltar',
                                options: FFButtonOptions(
                                  width: 102,
                                  height: 25,
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      16, 0, 16, 0),
                                  iconPadding: EdgeInsetsDirectional.fromSTEB(
                                      140, 0, 0, 0),
                                  color: Color(0xFF246536),
                                  textStyle: FlutterFlowTheme.of(context)
                                      .titleSmall
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        letterSpacing: 0.0,
                                      ),
                                  elevation: 0,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(20),
                                    bottomRight: Radius.circular(20),
                                    topLeft: Radius.circular(20),
                                    topRight: Radius.circular(20),
                                  ),
                                ),
                              ),
                            ),
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(150, 0, 0, 0),
                              child: FFButtonWidget(
                                onPressed: () async {
                                  await UsuariosRecord.collection
                                      .doc()
                                      .set(createUsuariosRecordData(
                                        tipoExame: _model.dropDownValue1,
                                        unidade: _model.dropDownValue2,
                                        horaExame: _model.dropDownValue3,
                                        dataExame:
                                            _model.calendarSelectedDay?.start,
                                      ));

                                  context.goNamed(
                                    'SaudeAgeSucesso',
                                    extra: <String, dynamic>{
                                      kTransitionInfoKey: TransitionInfo(
                                        hasTransition: true,
                                        transitionType:
                                            PageTransitionType.bottomToTop,
                                      ),
                                    },
                                  );
                                },
                                text: 'Agendar',
                                options: FFButtonOptions(
                                  width: 110,
                                  height: 25,
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      20, 0, 16, 0),
                                  iconPadding: EdgeInsetsDirectional.fromSTEB(
                                      140, 0, 0, 0),
                                  color: Color(0xFF246536),
                                  textStyle: FlutterFlowTheme.of(context)
                                      .titleSmall
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        letterSpacing: 0.0,
                                      ),
                                  elevation: 0,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(20),
                                    bottomRight: Radius.circular(20),
                                    topLeft: Radius.circular(20),
                                    topRight: Radius.circular(20),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ],
                  ),
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
}

# **Agendamento Exames sucesso**

import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_age_sucesso_model.dart';
export 'saude_age_sucesso_model.dart';

class SaudeAgeSucessoWidget extends StatefulWidget {
  const SaudeAgeSucessoWidget({super.key});

  @override
  State<SaudeAgeSucessoWidget> createState() => _SaudeAgeSucessoWidgetState();
}

class _SaudeAgeSucessoWidgetState extends State<SaudeAgeSucessoWidget> {
  late SaudeAgeSucessoModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeAgeSucessoModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Align(
          alignment: AlignmentDirectional(0, -1),
          child: Padding(
            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
            child: Container(
              width: 462,
              height: 967,
              decoration: BoxDecoration(
                gradient: LinearGradient(
                  colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                  stops: [0, 1],
                  begin: AlignmentDirectional(0, -1),
                  end: AlignmentDirectional(0, 1),
                ),
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(32),
                  bottomRight: Radius.circular(32),
                  topLeft: Radius.circular(32),
                  topRight: Radius.circular(32),
                ),
                shape: BoxShape.rectangle,
              ),
              alignment: AlignmentDirectional(0, 0),
              child: Align(
                alignment: AlignmentDirectional(0, -1),
                child: Padding(
                  padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
                  child: Column(
                    mainAxisSize: MainAxisSize.max,
                    children: [
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 67, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Align(
                              alignment: AlignmentDirectional(-1, -1),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(6, 0, 0, 0),
                                child: ClipRRect(
                                  borderRadius: BorderRadius.circular(8),
                                  child: Image.asset(
                                    'assets/images/saude-removebg-preview.png',
                                    width: 70,
                                    height: 70,
                                    fit: BoxFit.fill,
                                    alignment: Alignment(-1, -1),
                                  ),
                                ),
                              ),
                            ),
                            Align(
                              alignment: AlignmentDirectional(-1, -1),
                              child: Container(
                                width: 271,
                                height: 25,
                                decoration: BoxDecoration(
                                  color: Color(0xFF246536),
                                  borderRadius: BorderRadius.circular(24),
                                  shape: BoxShape.rectangle,
                                ),
                                alignment: AlignmentDirectional(0, -1),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Text(
                                    'AGENDAMENTO DE EXAMES',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color:
                                              FlutterFlowTheme.of(context).info,
                                          fontSize: 15,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 150, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Padding(
                              padding:
                                  EdgeInsetsDirectional.fromSTEB(15, 0, 0, 0),
                              child: Container(
                                width: 363,
                                height: 179,
                                decoration: BoxDecoration(),
                                child: Column(
                                  mainAxisSize: MainAxisSize.max,
                                  children: [
                                    Padding(
                                      padding: EdgeInsetsDirectional.fromSTEB(
                                          0, 2, 0, 0),
                                      child: Column(
                                        mainAxisSize: MainAxisSize.max,
                                        children: [
                                          Align(
                                            alignment:
                                                AlignmentDirectional(0, 0),
                                            child: Container(
                                              width: 350,
                                              height: 25,
                                              decoration: BoxDecoration(
                                                color: Color(0xFF153A71),
                                                borderRadius: BorderRadius.only(
                                                  bottomLeft:
                                                      Radius.circular(0),
                                                  bottomRight:
                                                      Radius.circular(0),
                                                  topLeft: Radius.circular(17),
                                                  topRight: Radius.circular(17),
                                                ),
                                              ),
                                              alignment:
                                                  AlignmentDirectional(0, 0),
                                            ),
                                          ),
                                          Align(
                                            alignment:
                                                AlignmentDirectional(0, -1),
                                            child: Container(
                                              width: 351,
                                              height: 130,
                                              decoration: BoxDecoration(
                                                color:
                                                    FlutterFlowTheme.of(context)
                                                        .secondaryBackground,
                                                borderRadius: BorderRadius.only(
                                                  bottomLeft:
                                                      Radius.circular(17),
                                                  bottomRight:
                                                      Radius.circular(17),
                                                  topLeft: Radius.circular(0),
                                                  topRight: Radius.circular(0),
                                                ),
                                              ),
                                              alignment:
                                                  AlignmentDirectional(0, -1),
                                              child: Align(
                                                alignment:
                                                    AlignmentDirectional(0, 0),
                                                child: Padding(
                                                  padding: EdgeInsetsDirectional
                                                      .fromSTEB(10, 0, 10, 0),
                                                  child: Text(
                                                    'Agendamento do exame realizado com sucesso!',
                                                    textAlign: TextAlign.center,
                                                    style: FlutterFlowTheme.of(
                                                            context)
                                                        .bodyMedium
                                                        .override(
                                                          fontFamily: 'Rubik',
                                                          color:
                                                              Color(0xFF153A71),
                                                          fontSize: 20,
                                                          letterSpacing: 0.0,
                                                          fontWeight:
                                                              FontWeight.w600,
                                                        ),
                                                  ),
                                                ),
                                              ),
                                            ),
                                          ),
                                        ],
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(0, 100, 0, 0),
                        child: Row(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Align(
                              alignment: AlignmentDirectional(0, 0),
                              child: Padding(
                                padding: EdgeInsetsDirectional.fromSTEB(
                                    160, 0, 0, 0),
                                child: Wrap(
                                  spacing: 0,
                                  runSpacing: 0,
                                  alignment: WrapAlignment.start,
                                  crossAxisAlignment: WrapCrossAlignment.start,
                                  direction: Axis.horizontal,
                                  runAlignment: WrapAlignment.start,
                                  verticalDirection: VerticalDirection.down,
                                  clipBehavior: Clip.none,
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(1, 0),
                                      child: FFButtonWidget(
                                        onPressed: () async {
                                          context.pushNamed('SaudeOla');
                                        },
                                        text: 'Voltar',
                                        options: FFButtonOptions(
                                          height: 22,
                                          padding:
                                              EdgeInsetsDirectional.fromSTEB(
                                                  19, 0, 16, 0),
                                          iconPadding:
                                              EdgeInsetsDirectional.fromSTEB(
                                                  0, 0, 0, 0),
                                          color: Color(0xFF246536),
                                          textStyle:
                                              FlutterFlowTheme.of(context)
                                                  .titleSmall
                                                  .override(
                                                    fontFamily: 'Rubik',
                                                    color: Colors.white,
                                                    letterSpacing: 0.0,
                                                  ),
                                          elevation: 0,
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(20),
                                            bottomRight: Radius.circular(20),
                                            topLeft: Radius.circular(20),
                                            topRight: Radius.circular(20),
                                          ),
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ],
                  ),
                ),
              ),
            ),
          ),
        ),
      ),
    );
  }
}


# **Histórico Paciente**

import '/backend/backend.dart';
import '/flutter_flow/flutter_flow_drop_down.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import '/flutter_flow/form_field_controller.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_historico_model.dart';
export 'saude_historico_model.dart';

class SaudeHistoricoWidget extends StatefulWidget {
  const SaudeHistoricoWidget({super.key});

  @override
  State<SaudeHistoricoWidget> createState() => _SaudeHistoricoWidgetState();
}

class _SaudeHistoricoWidgetState extends State<SaudeHistoricoWidget> {
  late SaudeHistoricoModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeHistoricoModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Container(
          width: double.infinity,
          height: double.infinity,
          decoration: BoxDecoration(
            gradient: LinearGradient(
              colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
              stops: [0, 1],
              begin: AlignmentDirectional(0, -1),
              end: AlignmentDirectional(0, 1),
            ),
            borderRadius: BorderRadius.circular(32),
          ),
          child: Column(
            mainAxisSize: MainAxisSize.max,
            children: [
              Row(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 12),
                    child: ClipRRect(
                      borderRadius: BorderRadius.circular(8),
                      child: Image.asset(
                        'assets/images/Logo+Saude.png',
                        width: 70,
                        height: 70,
                        fit: BoxFit.cover,
                      ),
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(23, 70, 0, 0),
                    child: Container(
                      width: 244,
                      height: 28,
                      decoration: BoxDecoration(
                        color: Color(0xFF246536),
                        borderRadius: BorderRadius.only(
                          bottomLeft: Radius.circular(32),
                          bottomRight: Radius.circular(32),
                          topLeft: Radius.circular(32),
                          topRight: Radius.circular(32),
                        ),
                      ),
                      child: Align(
                        alignment: AlignmentDirectional(0, 0),
                        child: Text(
                          'HISTÓRICO DO PACIENTE',
                          textAlign: TextAlign.center,
                          style:
                              FlutterFlowTheme.of(context).bodyMedium.override(
                                    fontFamily: 'Inter',
                                    color: Colors.white,
                                    fontSize: 17,
                                    letterSpacing: 0.0,
                                    fontWeight: FontWeight.w600,
                                  ),
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Align(
                    alignment: AlignmentDirectional(0, 0),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(14, 12, 0, 0),
                      child: Container(
                        width: 369,
                        height: 65,
                        decoration: BoxDecoration(),
                        child: Column(
                          mainAxisSize: MainAxisSize.max,
                          children: [
                            Align(
                              alignment: AlignmentDirectional(-0.17, -0.56),
                              child: Container(
                                width: 381,
                                height: 14,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(14),
                                    topRight: Radius.circular(14),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(-0.92, -1),
                                  child: Text(
                                    'Consultas Agendadas',
                                    textAlign: TextAlign.start,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w500,
                                        ),
                                  ),
                                ),
                              ),
                            ),
                            Align(
                              alignment: AlignmentDirectional(-0.17, -0.54),
                              child: Container(
                                width: 381,
                                height: 40,
                                decoration: BoxDecoration(
                                  color: Color(0xFFD9D9D9),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(14),
                                    bottomRight: Radius.circular(14),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: StreamBuilder<List<UsuariosRecord>>(
                                  stream: queryUsuariosRecord(
                                    queryBuilder: (usuariosRecord) =>
                                        usuariosRecord.where(
                                      'especialidade',
                                      isEqualTo: _model.dropDownValue1,
                                    ),
                                    singleRecord: true,
                                  ),
                                  builder: (context, snapshot) {
                                    // Customize what your widget looks like when it's loading.
                                    if (!snapshot.hasData) {
                                      return Center(
                                        child: SizedBox(
                                          width: 50,
                                          height: 50,
                                          child: CircularProgressIndicator(
                                            valueColor:
                                                AlwaysStoppedAnimation<Color>(
                                              FlutterFlowTheme.of(context)
                                                  .primary,
                                            ),
                                          ),
                                        ),
                                      );
                                    }
                                    List<UsuariosRecord>
                                        dropDownUsuariosRecordList =
                                        snapshot.data!;
                                    // Return an empty Container when the item does not exist.
                                    if (snapshot.data!.isEmpty) {
                                      return Container();
                                    }
                                    final dropDownUsuariosRecord =
                                        dropDownUsuariosRecordList.isNotEmpty
                                            ? dropDownUsuariosRecordList.first
                                            : null;

                                    return FlutterFlowDropDown<String>(
                                      controller:
                                          _model.dropDownValueController1 ??=
                                              FormFieldController<String>(
                                        _model.dropDownValue1 ??= '',
                                      ),
                                      options: List<String>.from([
                                        'Ortopedista, Hospital Geral 27/11/2024 - 14:00'
                                      ]),
                                      optionLabels: [
                                        'Ortopedista, Hospital Geral 27/11/2024 - 14:00'
                                      ],
                                      onChanged: (val) => safeSetState(
                                          () => _model.dropDownValue1 = val),
                                      width: 200,
                                      height: 71,
                                      textStyle: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Inter',
                                            letterSpacing: 0.0,
                                          ),
                                      icon: Icon(
                                        Icons.arrow_drop_down_circle_outlined,
                                        color: Color(0xFF246536),
                                        size: 15,
                                      ),
                                      fillColor: Color(0xFFD9D9D9),
                                      elevation: 2,
                                      borderColor: Colors.transparent,
                                      borderWidth: 0,
                                      borderRadius: 8,
                                      margin: EdgeInsetsDirectional.fromSTEB(
                                          12, 0, 12, 0),
                                      hidesUnderline: true,
                                      isOverButton: false,
                                      isSearchable: false,
                                      isMultiSelect: false,
                                    );
                                  },
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                    child: Container(
                      width: 369,
                      height: 63,
                      decoration: BoxDecoration(),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Align(
                            alignment: AlignmentDirectional(-0.17, -0.56),
                            child: Container(
                              width: 381,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(14),
                                  topRight: Radius.circular(14),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-0.92, -1),
                                child: Text(
                                  'Exames Agendadas',
                                  textAlign: TextAlign.start,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w500,
                                      ),
                                ),
                              ),
                            ),
                          ),
                          Align(
                            alignment: AlignmentDirectional(-0.17, -0.54),
                            child: Container(
                              width: 381,
                              height: 40,
                              decoration: BoxDecoration(
                                color: Color(0xFFD9D9D9),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(14),
                                  bottomRight: Radius.circular(14),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: StreamBuilder<List<UsuariosRecord>>(
                                stream: queryUsuariosRecord(
                                  singleRecord: true,
                                ),
                                builder: (context, snapshot) {
                                  // Customize what your widget looks like when it's loading.
                                  if (!snapshot.hasData) {
                                    return Center(
                                      child: SizedBox(
                                        width: 50,
                                        height: 50,
                                        child: CircularProgressIndicator(
                                          valueColor:
                                              AlwaysStoppedAnimation<Color>(
                                            FlutterFlowTheme.of(context)
                                                .primary,
                                          ),
                                        ),
                                      ),
                                    );
                                  }
                                  List<UsuariosRecord>
                                      dropDownUsuariosRecordList =
                                      snapshot.data!;
                                  // Return an empty Container when the item does not exist.
                                  if (snapshot.data!.isEmpty) {
                                    return Container();
                                  }
                                  final dropDownUsuariosRecord =
                                      dropDownUsuariosRecordList.isNotEmpty
                                          ? dropDownUsuariosRecordList.first
                                          : null;

                                  return FlutterFlowDropDown<String>(
                                    controller:
                                        _model.dropDownValueController2 ??=
                                            FormFieldController<String>(
                                      _model.dropDownValue2 ??= '',
                                    ),
                                    options: List<String>.from([
                                      'Creatinina, Laboratorio Centro 03/12/2024 - 9:30'
                                    ]),
                                    optionLabels: [
                                      'Raio-X, Laboratorio Centro 03/12/2024 - 9:30'
                                    ],
                                    onChanged: (val) => safeSetState(
                                        () => _model.dropDownValue2 = val),
                                    width: 200,
                                    height: 71,
                                    textStyle: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          letterSpacing: 0.0,
                                        ),
                                    icon: Icon(
                                      Icons.arrow_drop_down_circle_outlined,
                                      color: Color(0xFF246536),
                                      size: 15,
                                    ),
                                    fillColor: Color(0xFFD9D9D9),
                                    elevation: 2,
                                    borderColor: Colors.transparent,
                                    borderWidth: 0,
                                    borderRadius: 8,
                                    margin: EdgeInsetsDirectional.fromSTEB(
                                        12, 0, 12, 0),
                                    hidesUnderline: true,
                                    isOverButton: false,
                                    isSearchable: false,
                                    isMultiSelect: false,
                                  );
                                },
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                    child: Container(
                      width: 369,
                      height: 63,
                      decoration: BoxDecoration(),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Align(
                            alignment: AlignmentDirectional(-0.17, -0.56),
                            child: Container(
                              width: 381,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(14),
                                  topRight: Radius.circular(14),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-0.92, -1),
                                child: Text(
                                  'Consultas Realizadas',
                                  textAlign: TextAlign.start,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w500,
                                      ),
                                ),
                              ),
                            ),
                          ),
                          Align(
                            alignment: AlignmentDirectional(-0.17, -0.54),
                            child: Container(
                              width: 381,
                              height: 40,
                              decoration: BoxDecoration(
                                color: Color(0xFFD9D9D9),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(14),
                                  bottomRight: Radius.circular(14),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: FlutterFlowDropDown<String>(
                                controller: _model.dropDownValueController3 ??=
                                    FormFieldController<String>(null),
                                options: [''],
                                onChanged: (val) => safeSetState(
                                    () => _model.dropDownValue3 = val),
                                width: 200,
                                height: 71,
                                textStyle: FlutterFlowTheme.of(context)
                                    .bodyMedium
                                    .override(
                                      fontFamily: 'Inter',
                                      letterSpacing: 0.0,
                                    ),
                                icon: Icon(
                                  Icons.arrow_drop_down_circle_outlined,
                                  color: Color(0xFF246536),
                                  size: 15,
                                ),
                                fillColor: Color(0xFFD9D9D9),
                                elevation: 2,
                                borderColor: Colors.transparent,
                                borderWidth: 0,
                                borderRadius: 8,
                                margin: EdgeInsetsDirectional.fromSTEB(
                                    12, 0, 12, 0),
                                hidesUnderline: true,
                                isOverButton: false,
                                isSearchable: false,
                                isMultiSelect: false,
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
              Row(
                mainAxisSize: MainAxisSize.max,
                mainAxisAlignment: MainAxisAlignment.start,
                children: [
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(14, 0, 0, 0),
                    child: Container(
                      width: 369,
                      height: 63,
                      decoration: BoxDecoration(),
                      child: Column(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Align(
                            alignment: AlignmentDirectional(-0.17, -0.56),
                            child: Container(
                              width: 381,
                              height: 14,
                              decoration: BoxDecoration(
                                color: Color(0xFF153A71),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(0),
                                  bottomRight: Radius.circular(0),
                                  topLeft: Radius.circular(14),
                                  topRight: Radius.circular(14),
                                ),
                              ),
                              child: Align(
                                alignment: AlignmentDirectional(-0.92, -1),
                                child: Text(
                                  'Exames Realizados',
                                  textAlign: TextAlign.start,
                                  style: FlutterFlowTheme.of(context)
                                      .bodyMedium
                                      .override(
                                        fontFamily: 'Rubik',
                                        color: Colors.white,
                                        fontSize: 12,
                                        letterSpacing: 0.0,
                                        fontWeight: FontWeight.w500,
                                      ),
                                ),
                              ),
                            ),
                          ),
                          Align(
                            alignment: AlignmentDirectional(-0.17, -0.54),
                            child: Container(
                              width: 381,
                              height: 40,
                              decoration: BoxDecoration(
                                color: Color(0xFFD9D9D9),
                                borderRadius: BorderRadius.only(
                                  bottomLeft: Radius.circular(14),
                                  bottomRight: Radius.circular(14),
                                  topLeft: Radius.circular(0),
                                  topRight: Radius.circular(0),
                                ),
                              ),
                              child: FlutterFlowDropDown<String>(
                                controller: _model.dropDownValueController4 ??=
                                    FormFieldController<String>(null),
                                options: [''],
                                onChanged: (val) => safeSetState(
                                    () => _model.dropDownValue4 = val),
                                width: 200,
                                height: 71,
                                textStyle: FlutterFlowTheme.of(context)
                                    .bodyMedium
                                    .override(
                                      fontFamily: 'Inter',
                                      letterSpacing: 0.0,
                                    ),
                                icon: Icon(
                                  Icons.arrow_drop_down_circle_outlined,
                                  color: Color(0xFF246536),
                                  size: 15,
                                ),
                                fillColor: Color(0xFFD9D9D9),
                                elevation: 2,
                                borderColor: Colors.transparent,
                                borderWidth: 0,
                                borderRadius: 8,
                                margin: EdgeInsetsDirectional.fromSTEB(
                                    12, 0, 12, 0),
                                hidesUnderline: true,
                                isOverButton: false,
                                isSearchable: false,
                                isMultiSelect: false,
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
              SingleChildScrollView(
                scrollDirection: Axis.horizontal,
                child: Row(
                  mainAxisSize: MainAxisSize.max,
                  children: [
                    Align(
                      alignment: AlignmentDirectional(0, 0.25),
                      child: FFButtonWidget(
                        onPressed: () async {
                          context.pushNamed('SaudeOla');
                        },
                        text: 'Voltar',
                        options: FFButtonOptions(
                          width: 95,
                          height: 19,
                          padding: EdgeInsetsDirectional.fromSTEB(16, 0, 16, 0),
                          iconPadding:
                              EdgeInsetsDirectional.fromSTEB(0, 0, 0, 0),
                          color: Color(0xFF246536),
                          textStyle:
                              FlutterFlowTheme.of(context).titleSmall.override(
                                    fontFamily: 'Rubik',
                                    color: Colors.white,
                                    fontSize: 15,
                                    letterSpacing: 0.0,
                                    fontWeight: FontWeight.w500,
                                  ),
                          elevation: 0,
                          borderRadius: BorderRadius.only(
                            bottomLeft: Radius.circular(32),
                            bottomRight: Radius.circular(32),
                            topLeft: Radius.circular(32),
                            topRight: Radius.circular(32),
                          ),
                        ),
                      ),
                    ),
                  ],
                ),
              ),
            ].divide(SizedBox(height: 12)),
          ),
        ),
      ),
    );
  }
}


# **Saúde Dicas**

import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_dicas_model.dart';
export 'saude_dicas_model.dart';

class SaudeDicasWidget extends StatefulWidget {
  const SaudeDicasWidget({super.key});

  @override
  State<SaudeDicasWidget> createState() => _SaudeDicasWidgetState();
}

class _SaudeDicasWidgetState extends State<SaudeDicasWidget> {
  late SaudeDicasModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeDicasModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Align(
          alignment: AlignmentDirectional(0, -1),
          child: Padding(
            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
            child: Container(
              width: 462,
              height: 967,
              decoration: BoxDecoration(
                gradient: LinearGradient(
                  colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                  stops: [0, 1],
                  begin: AlignmentDirectional(0, -1),
                  end: AlignmentDirectional(0, 1),
                ),
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(32),
                  bottomRight: Radius.circular(32),
                  topLeft: Radius.circular(32),
                  topRight: Radius.circular(32),
                ),
              ),
              child: Column(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Row(
                    mainAxisSize: MainAxisSize.max,
                    children: [
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 0),
                        child: ClipRRect(
                          borderRadius: BorderRadius.circular(8),
                          child: Image.asset(
                            'assets/images/MaisSaude2.png',
                            width: 70,
                            height: 70,
                            fit: BoxFit.cover,
                          ),
                        ),
                      ),
                      Flexible(
                        child: Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(5, 70, 0, 0),
                          child: Container(
                            width: 290,
                            height: 28,
                            decoration: BoxDecoration(
                              color: Color(0xFF246536),
                              borderRadius: BorderRadius.only(
                                bottomLeft: Radius.circular(32),
                                bottomRight: Radius.circular(32),
                                topLeft: Radius.circular(32),
                                topRight: Radius.circular(32),
                              ),
                            ),
                            child: Align(
                              alignment: AlignmentDirectional(0, 0),
                              child: Text(
                                'INFORMAÇÕES E DICAS DE SAÚDE',
                                textAlign: TextAlign.center,
                                style: FlutterFlowTheme.of(context)
                                    .bodyMedium
                                    .override(
                                      fontFamily: 'Rubik',
                                      color: Colors.white,
                                      fontSize: 16,
                                      letterSpacing: 0.0,
                                      fontWeight: FontWeight.w600,
                                    ),
                              ),
                            ),
                          ),
                        ),
                      ),
                    ],
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 20, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 28,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                  child: Align(
                                    alignment: AlignmentDirectional(0, 0),
                                    child: Text(
                                      'Doenças infecto Contagiosas',
                                      textAlign: TextAlign.center,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Colors.white,
                                            fontSize: 10,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 82,
                                  decoration: BoxDecoration(
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(15),
                                      bottomRight: Radius.circular(15),
                                      topLeft: Radius.circular(0),
                                      topRight: Radius.circular(0),
                                    ),
                                  ),
                                  child: Align(
                                    alignment: AlignmentDirectional(0, 0),
                                    child: ClipRRect(
                                      borderRadius: BorderRadius.circular(8),
                                      child: Image.asset(
                                        'assets/images/bacterias_virus_e_fungos.png',
                                        width: 70,
                                        height: 70,
                                        fit: BoxFit.scaleDown,
                                      ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 97,
                                height: 28,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Text(
                                    'Vacinas',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Inter',
                                          color: Colors.white,
                                          fontSize: 10,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 97,
                                height: 82,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: ClipRRect(
                                    borderRadius: BorderRadius.circular(8),
                                    child: Image.asset(
                                      'assets/images/Vacinas.png',
                                      width: 70,
                                      height: 70,
                                      fit: BoxFit.scaleDown,
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 97,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Text(
                                    'Saúde Mental',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 10,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 97,
                                height: 81,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: ClipRRect(
                                    borderRadius: BorderRadius.circular(8),
                                    child: Image.asset(
                                      'assets/images/saude_mental.png',
                                      width: 70,
                                      height: 70,
                                      fit: BoxFit.scaleDown,
                                      alignment: Alignment(0, 0),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ],
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 21, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 29,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                  child: Align(
                                    alignment: AlignmentDirectional(0, 0),
                                    child: Text(
                                      'Gravidez e              Pré Natal',
                                      textAlign: TextAlign.center,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Colors.white,
                                            fontSize: 10,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 97,
                                  height: 83,
                                  decoration: BoxDecoration(
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(15),
                                      bottomRight: Radius.circular(15),
                                      topLeft: Radius.circular(0),
                                      topRight: Radius.circular(0),
                                    ),
                                  ),
                                  child: Align(
                                    alignment: AlignmentDirectional(0, 0),
                                    child: ClipRRect(
                                      borderRadius: BorderRadius.circular(8),
                                      child: Image.asset(
                                        'assets/images/Saude_e_gestaao.png',
                                        width: 70,
                                        height: 70,
                                        fit: BoxFit.scaleDown,
                                      ),
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 97,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Text(
                                    'Alimentação Saudável',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 11,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 97,
                                height: 83,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: ClipRRect(
                                    borderRadius: BorderRadius.circular(8),
                                    child: Image.asset(
                                      'assets/images/alimentao_e_saude.png',
                                      width: 70,
                                      height: 70,
                                      fit: BoxFit.scaleDown,
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(25, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 97,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Text(
                                    'Saúde e              Bem Estar',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 11,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 97,
                                height: 83,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: ClipRRect(
                                    borderRadius: BorderRadius.circular(8),
                                    child: Image.asset(
                                      'assets/images/saude_e_bem_estar.png',
                                      width: 70,
                                      height: 70,
                                      fit: BoxFit.scaleDown,
                                    ),
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                      ],
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(-1, -1),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(0, 40, 0, 0),
                      child: Row(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Flexible(
                            child: Align(
                              alignment: AlignmentDirectional(0, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                                child: FFButtonWidget(
                                  onPressed: () async {
                                    context.pushNamed('SaudeOla');
                                  },
                                  text: 'Voltar',
                                  options: FFButtonOptions(
                                    width: 130,
                                    height: 25,
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        3, 0, 0, 0),
                                    iconPadding: EdgeInsetsDirectional.fromSTEB(
                                        0, 0, 0, 0),
                                    color: Color(0xFF246536),
                                    textStyle: FlutterFlowTheme.of(context)
                                        .titleSmall
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 17,
                                          letterSpacing: 0.0,
                                        ),
                                    elevation: 0,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(20),
                                      bottomRight: Radius.circular(20),
                                      topLeft: Radius.circular(20),
                                      topRight: Radius.circular(20),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}


# **Saúde Suporte**

import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_suporte_model.dart';
export 'saude_suporte_model.dart';

class SaudeSuporteWidget extends StatefulWidget {
  const SaudeSuporteWidget({super.key});

  @override
  State<SaudeSuporteWidget> createState() => _SaudeSuporteWidgetState();
}

class _SaudeSuporteWidgetState extends State<SaudeSuporteWidget> {
  late SaudeSuporteModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeSuporteModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Stack(
          children: [
            Align(
              alignment: AlignmentDirectional(0, 0),
              child: Stack(
                children: [
                  Stack(
                    children: [
                      Container(
                        width: 445,
                        height: 933,
                        decoration: BoxDecoration(
                          gradient: LinearGradient(
                            colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                            stops: [0, 1],
                            begin: AlignmentDirectional(0, -1),
                            end: AlignmentDirectional(0, 1),
                          ),
                          borderRadius: BorderRadius.circular(30),
                        ),
                        child: Stack(
                          children: [
                            Align(
                              alignment: AlignmentDirectional(0, 0),
                              child: Container(
                                width: 370,
                                child: Stack(
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(0, -0.37),
                                      child: Container(
                                        width: 400,
                                        height: 335,
                                        decoration: BoxDecoration(
                                          color: Color(0xFF153A71),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(14),
                                            bottomRight: Radius.circular(14),
                                            topLeft: Radius.circular(14),
                                            topRight: Radius.circular(14),
                                          ),
                                        ),
                                      ),
                                    ),
                                    Align(
                                      alignment: AlignmentDirectional(0, -0.3),
                                      child: Container(
                                        width: 400,
                                        height: 313,
                                        decoration: BoxDecoration(
                                          color: Color(0xFFD9D9D9),
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(14),
                                            bottomRight: Radius.circular(14),
                                            topLeft: Radius.circular(0),
                                            topRight: Radius.circular(0),
                                          ),
                                        ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(-0.01, 0.28),
                                      child: FFButtonWidget(
                                        onPressed: () async {
                                          context.pushNamed('SaudeOla');
                                        },
                                        text: 'Voltar',
                                        options: FFButtonOptions(
                                          width: 95,
                                          height: 19,
                                          padding:
                                              EdgeInsetsDirectional.fromSTEB(
                                                  16, 0, 16, 0),
                                          iconPadding:
                                              EdgeInsetsDirectional.fromSTEB(
                                                  0, 0, 0, 0),
                                          color: Color(0xFF246536),
                                          textStyle:
                                              FlutterFlowTheme.of(context)
                                                  .titleSmall
                                                  .override(
                                                    fontFamily: 'Rubik',
                                                    color: Colors.white,
                                                    fontSize: 15,
                                                    letterSpacing: 0.0,
                                                    fontWeight: FontWeight.w500,
                                                  ),
                                          elevation: 0,
                                          borderRadius: BorderRadius.only(
                                            bottomLeft: Radius.circular(32),
                                            bottomRight: Radius.circular(32),
                                            topLeft: Radius.circular(32),
                                            topRight: Radius.circular(32),
                                          ),
                                        ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(0.42, -0.39),
                                      child: Text(
                                        'Telefone + SAÚDE    - 5555-5555\nTelefone HOSPITAL - 5555-5555\nTelefone CLÍNICA     - 5555-5555',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color: Color(0xFF153A71),
                                              fontSize: 15,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(-0.09, -0.14),
                                      child: Text(
                                        'Chat + SAÚDE  - \nWhatsApp + SAÚDE  - \nEmail + SAÚDE:  ',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color: Color(0xFF153A71),
                                              fontSize: 15,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(0.47, -0.18),
                                      child: Text(
                                        'clique aqui',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color: Color(0xFF246536),
                                              fontSize: 15,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(0.86, -0.13),
                                      child: Text(
                                        '95555-5555 ',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color: Color(0xFF246536),
                                              fontSize: 15,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(0.7, -0.05),
                                      child: Text(
                                        'maissaude@maissaude.com.br ',
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color: Color(0xFF246536),
                                              fontSize: 17,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(-0.87, -0.4),
                                      child: ClipRRect(
                                        borderRadius: BorderRadius.circular(8),
                                        child: Image.asset(
                                          'assets/images/5ccaf87d5c77fad1d9aa9472fb48a1ab.png',
                                          width: 60,
                                          height: 60,
                                          fit: BoxFit.contain,
                                        ),
                                      ),
                                    ),
                                    Align(
                                      alignment:
                                          AlignmentDirectional(-0.85, -0.12),
                                      child: ClipRRect(
                                        borderRadius: BorderRadius.circular(8),
                                        child: Image.asset(
                                          'assets/images/CELL.png',
                                          width: 60,
                                          height: 60,
                                          fit: BoxFit.contain,
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ),
                          ],
                        ),
                      ),
                    ],
                  ),
                  Align(
                    alignment: AlignmentDirectional(0.5, -0.75),
                    child: Container(
                      width: 254,
                      height: 25,
                      decoration: BoxDecoration(
                        color: Color(0xFF246536),
                        borderRadius: BorderRadius.only(
                          bottomLeft: Radius.circular(32),
                          bottomRight: Radius.circular(32),
                          topLeft: Radius.circular(32),
                          topRight: Radius.circular(32),
                        ),
                      ),
                      alignment: AlignmentDirectional(0, 0),
                      child: Align(
                        alignment: AlignmentDirectional(0, 0),
                        child: Text(
                          'AJUDA E SUPORTE',
                          textAlign: TextAlign.center,
                          style:
                              FlutterFlowTheme.of(context).bodyMedium.override(
                                    fontFamily: 'Rubik',
                                    color: Colors.white,
                                    fontSize: 18,
                                    letterSpacing: 0.0,
                                    fontWeight: FontWeight.w500,
                                  ),
                        ),
                      ),
                    ),
                  ),
                ],
              ),
            ),
            Align(
              alignment: AlignmentDirectional(-0.93, -0.81),
              child: ClipRRect(
                borderRadius: BorderRadius.circular(8),
                child: Image.asset(
                  'assets/images/MaisSaude2.png',
                  width: 70.9,
                  height: 70.65,
                  fit: BoxFit.cover,
                ),
              ),
            ),
          ],
        ),
      ),
    );
  }
}


# **Excluir ou Editar**

import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_excluir_editar_model.dart';
export 'saude_excluir_editar_model.dart';

class SaudeExcluirEditarWidget extends StatefulWidget {
  const SaudeExcluirEditarWidget({super.key});

  @override
  State<SaudeExcluirEditarWidget> createState() =>
      _SaudeExcluirEditarWidgetState();
}

class _SaudeExcluirEditarWidgetState extends State<SaudeExcluirEditarWidget> {
  late SaudeExcluirEditarModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeExcluirEditarModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Align(
          alignment: AlignmentDirectional(0, -1),
          child: Padding(
            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
            child: Container(
              width: 462,
              height: 967,
              decoration: BoxDecoration(
                gradient: LinearGradient(
                  colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                  stops: [0, 1],
                  begin: AlignmentDirectional(0, -1),
                  end: AlignmentDirectional(0, 1),
                ),
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(32),
                  bottomRight: Radius.circular(32),
                  topLeft: Radius.circular(32),
                  topRight: Radius.circular(32),
                ),
              ),
              child: Column(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Row(
                    mainAxisSize: MainAxisSize.max,
                    children: [
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 0),
                        child: ClipRRect(
                          borderRadius: BorderRadius.circular(8),
                          child: Image.asset(
                            'assets/images/MaisSaude2.png',
                            width: 70,
                            height: 70,
                            fit: BoxFit.cover,
                          ),
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(15, 70, 0, 0),
                        child: Container(
                          width: 274,
                          height: 28,
                          decoration: BoxDecoration(
                            color: Color(0xFF246536),
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(32),
                              bottomRight: Radius.circular(32),
                              topLeft: Radius.circular(32),
                              topRight: Radius.circular(32),
                            ),
                          ),
                          child: Text(
                            'O que deseja fazer?',
                            textAlign: TextAlign.center,
                            style: FlutterFlowTheme.of(context)
                                .bodyMedium
                                .override(
                                  fontFamily: 'Rubik',
                                  color: Colors.white,
                                  fontSize: 21,
                                  letterSpacing: 0.0,
                                  fontWeight: FontWeight.w600,
                                ),
                          ),
                        ),
                      ),
                    ],
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 95, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      mainAxisAlignment: MainAxisAlignment.start,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(47, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 100,
                                  height: 28,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                  child: Padding(
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        0, 7, 0, 0),
                                    child: Text(
                                      'Excluir',
                                      textAlign: TextAlign.center,
                                      style: FlutterFlowTheme.of(context)
                                          .bodyMedium
                                          .override(
                                            fontFamily: 'Rubik',
                                            color: Colors.white,
                                            fontSize: 12,
                                            letterSpacing: 0.0,
                                            fontWeight: FontWeight.w600,
                                          ),
                                    ),
                                  ),
                                ),
                              ),
                              Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(10, 0, 0, 0),
                                child: Container(
                                  width: 100,
                                  height: 84,
                                  decoration: BoxDecoration(
                                    color: FlutterFlowTheme.of(context)
                                        .secondaryBackground,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(15),
                                      bottomRight: Radius.circular(15),
                                      topLeft: Radius.circular(0),
                                      topRight: Radius.circular(0),
                                    ),
                                  ),
                                  child: Stack(
                                    children: [
                                      Align(
                                        alignment: AlignmentDirectional(0, 0),
                                        child: ClipRRect(
                                          borderRadius:
                                              BorderRadius.circular(8),
                                          child: Image.asset(
                                            'assets/images/lixo2.png',
                                            width: 75,
                                            height: 75,
                                            fit: BoxFit.cover,
                                            alignment: Alignment(0, 0),
                                          ),
                                        ),
                                      ),
                                      Opacity(
                                        opacity: 0,
                                        child: Align(
                                          alignment: AlignmentDirectional(0, 0),
                                          child: FFButtonWidget(
                                            onPressed: () async {
                                              context
                                                  .pushNamed('SaudeExclusao');
                                            },
                                            text: 'Button',
                                            options: FFButtonOptions(
                                              width: 100,
                                              height: 90,
                                              padding: EdgeInsetsDirectional
                                                  .fromSTEB(16, 0, 16, 0),
                                              iconPadding: EdgeInsetsDirectional
                                                  .fromSTEB(0, 0, 0, 0),
                                              color:
                                                  FlutterFlowTheme.of(context)
                                                      .primary,
                                              textStyle:
                                                  FlutterFlowTheme.of(context)
                                                      .titleSmall
                                                      .override(
                                                        fontFamily:
                                                            'Inter Tight',
                                                        color: Colors.white,
                                                        letterSpacing: 0.0,
                                                      ),
                                              elevation: 0,
                                              borderRadius:
                                                  BorderRadius.circular(8),
                                            ),
                                          ),
                                        ),
                                      ),
                                    ],
                                  ),
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(80, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            crossAxisAlignment: CrossAxisAlignment.center,
                            children: [
                              Container(
                                width: 100,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 2, 0, 0),
                                  child: Text(
                                    'Editar Dados Cadastrais',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 12,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 100,
                                height: 84,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Stack(
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: Padding(
                                        padding: EdgeInsetsDirectional.fromSTEB(
                                            10, 0, 0, 0),
                                        child: ClipRRect(
                                          borderRadius:
                                              BorderRadius.circular(8),
                                          child: Image.asset(
                                            'assets/images/Editar.png',
                                            width: 75,
                                            height: 75,
                                            fit: BoxFit.cover,
                                          ),
                                        ),
                                      ),
                                    ),
                                    Opacity(
                                      opacity: 0,
                                      child: Align(
                                        alignment: AlignmentDirectional(0, 0),
                                        child: FFButtonWidget(
                                          onPressed: () async {
                                            context.pushNamed(
                                                'SaudeCadasrtroCopy');
                                          },
                                          text: 'Button',
                                          options: FFButtonOptions(
                                            width: 100,
                                            height: 90,
                                            padding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    16, 0, 16, 0),
                                            iconPadding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    0, 0, 0, 0),
                                            color: FlutterFlowTheme.of(context)
                                                .primary,
                                            textStyle:
                                                FlutterFlowTheme.of(context)
                                                    .titleSmall
                                                    .override(
                                                      fontFamily: 'Inter Tight',
                                                      color: Colors.white,
                                                      letterSpacing: 0.0,
                                                    ),
                                            elevation: 0,
                                            borderRadius:
                                                BorderRadius.circular(8),
                                          ),
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                      ],
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(-1, -1),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(20, 120, 0, 0),
                      child: Row(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Flexible(
                            child: Align(
                              alignment: AlignmentDirectional(0, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                                child: FFButtonWidget(
                                  onPressed: () async {
                                    context.pushNamed('SaudeOla');
                                  },
                                  text: 'Voltar',
                                  options: FFButtonOptions(
                                    width: 103,
                                    height: 22,
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        0, 0, 0, 0),
                                    iconPadding: EdgeInsetsDirectional.fromSTEB(
                                        0, 0, 0, 0),
                                    color: Color(0xFF246536),
                                    textStyle: FlutterFlowTheme.of(context)
                                        .titleSmall
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 16,
                                          letterSpacing: 0.0,
                                        ),
                                    elevation: 0,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(20),
                                      bottomRight: Radius.circular(20),
                                      topLeft: Radius.circular(20),
                                      topRight: Radius.circular(20),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}


# **Excluir Dados Cadastrais**

import '/auth/custom_auth/auth_util.dart';
import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_exclusao_model.dart';
export 'saude_exclusao_model.dart';

class SaudeExclusaoWidget extends StatefulWidget {
  const SaudeExclusaoWidget({super.key});

  @override
  State<SaudeExclusaoWidget> createState() => _SaudeExclusaoWidgetState();
}

class _SaudeExclusaoWidgetState extends State<SaudeExclusaoWidget> {
  late SaudeExclusaoModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeExclusaoModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Align(
          alignment: AlignmentDirectional(0, -1),
          child: Padding(
            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
            child: Container(
              width: 462,
              height: 967,
              decoration: BoxDecoration(
                gradient: LinearGradient(
                  colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                  stops: [0, 1],
                  begin: AlignmentDirectional(0, -1),
                  end: AlignmentDirectional(0, 1),
                ),
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(32),
                  bottomRight: Radius.circular(32),
                  topLeft: Radius.circular(32),
                  topRight: Radius.circular(32),
                ),
              ),
              child: Column(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Row(
                    mainAxisSize: MainAxisSize.max,
                    children: [
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 0),
                        child: ClipRRect(
                          borderRadius: BorderRadius.circular(8),
                          child: Image.asset(
                            'assets/images/MaisSaude2.png',
                            width: 70,
                            height: 70,
                            fit: BoxFit.cover,
                          ),
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(15, 70, 0, 0),
                        child: Container(
                          width: 274,
                          height: 28,
                          decoration: BoxDecoration(
                            color: Color(0xFF246536),
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(32),
                              bottomRight: Radius.circular(32),
                              topLeft: Radius.circular(32),
                              topRight: Radius.circular(32),
                            ),
                          ),
                          child: Text(
                            'Excluir dados Cadastrais',
                            textAlign: TextAlign.center,
                            style: FlutterFlowTheme.of(context)
                                .bodyMedium
                                .override(
                                  fontFamily: 'Rubik',
                                  color: Colors.white,
                                  fontSize: 21,
                                  letterSpacing: 0.0,
                                  fontWeight: FontWeight.w600,
                                ),
                          ),
                        ),
                      ),
                    ],
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Flexible(
                          child: Align(
                            alignment: AlignmentDirectional(0, 0),
                            child: Column(
                              mainAxisSize: MainAxisSize.max,
                              children: [
                                Container(
                                  width: 280,
                                  height: 22,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                ),
                                Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Container(
                                    width: 280,
                                    height: 101,
                                    decoration: BoxDecoration(
                                      color: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(15),
                                        bottomRight: Radius.circular(15),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    child: Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: Text(
                                        'Deseja realmente excluir seus dados cadastrais de forma permanente?',
                                        textAlign: TextAlign.center,
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color: Color(0xFF153A71),
                                              fontSize: 15,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                  ),
                                ),
                              ],
                            ),
                          ),
                        ),
                      ],
                    ),
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 21, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(55, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 100,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 8, 0, 0),
                                  child: Text(
                                    'Sim',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 11,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 100,
                                height: 84,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Stack(
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: ClipRRect(
                                        borderRadius: BorderRadius.circular(8),
                                        child: Image.asset(
                                          'assets/images/sim2.png',
                                          width: 75,
                                          height: 75,
                                          fit: BoxFit.cover,
                                        ),
                                      ),
                                    ),
                                    Opacity(
                                      opacity: 0,
                                      child: FFButtonWidget(
                                        onPressed: () async {
                                          context.pushNamed('SaudeExcEsc');
                                        },
                                        text: 'Button',
                                        options: FFButtonOptions(
                                          width: 100,
                                          height: 90,
                                          padding:
                                              EdgeInsetsDirectional.fromSTEB(
                                                  16, 0, 16, 0),
                                          iconPadding:
                                              EdgeInsetsDirectional.fromSTEB(
                                                  0, 0, 0, 0),
                                          color: FlutterFlowTheme.of(context)
                                              .primary,
                                          textStyle:
                                              FlutterFlowTheme.of(context)
                                                  .titleSmall
                                                  .override(
                                                    fontFamily: 'Inter Tight',
                                                    color: Colors.white,
                                                    letterSpacing: 0.0,
                                                  ),
                                          elevation: 0,
                                          borderRadius:
                                              BorderRadius.circular(8),
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                        Padding(
                          padding: EdgeInsetsDirectional.fromSTEB(80, 0, 0, 0),
                          child: Column(
                            mainAxisSize: MainAxisSize.max,
                            children: [
                              Container(
                                width: 100,
                                height: 29,
                                decoration: BoxDecoration(
                                  color: Color(0xFF153A71),
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(0),
                                    bottomRight: Radius.circular(0),
                                    topLeft: Radius.circular(15),
                                    topRight: Radius.circular(15),
                                  ),
                                ),
                                child: Padding(
                                  padding: EdgeInsetsDirectional.fromSTEB(
                                      0, 8, 0, 0),
                                  child: Text(
                                    'Não',
                                    textAlign: TextAlign.center,
                                    style: FlutterFlowTheme.of(context)
                                        .bodyMedium
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 11,
                                          letterSpacing: 0.0,
                                          fontWeight: FontWeight.w600,
                                        ),
                                  ),
                                ),
                              ),
                              Container(
                                width: 100,
                                height: 84,
                                decoration: BoxDecoration(
                                  color: FlutterFlowTheme.of(context)
                                      .secondaryBackground,
                                  borderRadius: BorderRadius.only(
                                    bottomLeft: Radius.circular(15),
                                    bottomRight: Radius.circular(15),
                                    topLeft: Radius.circular(0),
                                    topRight: Radius.circular(0),
                                  ),
                                ),
                                child: Stack(
                                  children: [
                                    Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: ClipRRect(
                                        borderRadius: BorderRadius.circular(8),
                                        child: Image.asset(
                                          'assets/images/No.png',
                                          width: 75,
                                          height: 75,
                                          fit: BoxFit.cover,
                                        ),
                                      ),
                                    ),
                                    Opacity(
                                      opacity: 0,
                                      child: Align(
                                        alignment: AlignmentDirectional(0, 0),
                                        child: FFButtonWidget(
                                          onPressed: () async {
                                            context.pushNamed('SaudeOla');
                                          },
                                          text: 'Button',
                                          options: FFButtonOptions(
                                            width: 100,
                                            height: 90,
                                            padding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    16, 0, 16, 0),
                                            iconPadding:
                                                EdgeInsetsDirectional.fromSTEB(
                                                    0, 0, 0, 0),
                                            color: FlutterFlowTheme.of(context)
                                                .primary,
                                            textStyle:
                                                FlutterFlowTheme.of(context)
                                                    .titleSmall
                                                    .override(
                                                      fontFamily: 'Inter Tight',
                                                      color: Colors.white,
                                                      letterSpacing: 0.0,
                                                    ),
                                            elevation: 0,
                                            borderRadius:
                                                BorderRadius.circular(8),
                                          ),
                                        ),
                                      ),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                      ],
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(-1, -1),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(20, 45, 0, 0),
                      child: Row(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Flexible(
                            child: Align(
                              alignment: AlignmentDirectional(0, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                                child: FFButtonWidget(
                                  onPressed: () async {
                                    context.pushNamed('SaudeOla');
                                  },
                                  text: 'Voltar',
                                  options: FFButtonOptions(
                                    width: 103,
                                    height: 22,
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        3, 0, 0, 0),
                                    iconPadding: EdgeInsetsDirectional.fromSTEB(
                                        0, 0, 0, 0),
                                    color: Color(0xFF246536),
                                    textStyle: FlutterFlowTheme.of(context)
                                        .titleSmall
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 16,
                                          letterSpacing: 0.0,
                                        ),
                                    elevation: 0,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(20),
                                      bottomRight: Radius.circular(20),
                                      topLeft: Radius.circular(20),
                                      topRight: Radius.circular(20),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}


# **Dados Excluidos com Sucessso**

import '/flutter_flow/flutter_flow_theme.dart';
import '/flutter_flow/flutter_flow_util.dart';
import '/flutter_flow/flutter_flow_widgets.dart';
import 'package:flutter/material.dart';
import 'package:google_fonts/google_fonts.dart';
import 'package:provider/provider.dart';

import 'saude_exc_esc_model.dart';
export 'saude_exc_esc_model.dart';

class SaudeExcEscWidget extends StatefulWidget {
  const SaudeExcEscWidget({super.key});

  @override
  State<SaudeExcEscWidget> createState() => _SaudeExcEscWidgetState();
}

class _SaudeExcEscWidgetState extends State<SaudeExcEscWidget> {
  late SaudeExcEscModel _model;

  final scaffoldKey = GlobalKey<ScaffoldState>();

  @override
  void initState() {
    super.initState();
    _model = createModel(context, () => SaudeExcEscModel());
  }

  @override
  void dispose() {
    _model.dispose();

    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () => FocusScope.of(context).unfocus(),
      child: Scaffold(
        key: scaffoldKey,
        backgroundColor: FlutterFlowTheme.of(context).primaryBackground,
        body: Align(
          alignment: AlignmentDirectional(0, -1),
          child: Padding(
            padding: EdgeInsetsDirectional.fromSTEB(0, 0, 1, 0),
            child: Container(
              width: 462,
              height: 967,
              decoration: BoxDecoration(
                gradient: LinearGradient(
                  colors: [Color(0xFF79DDF3), Color(0xFF5E845F)],
                  stops: [0, 1],
                  begin: AlignmentDirectional(0, -1),
                  end: AlignmentDirectional(0, 1),
                ),
                borderRadius: BorderRadius.only(
                  bottomLeft: Radius.circular(32),
                  bottomRight: Radius.circular(32),
                  topLeft: Radius.circular(32),
                  topRight: Radius.circular(32),
                ),
              ),
              child: Column(
                mainAxisSize: MainAxisSize.max,
                children: [
                  Row(
                    mainAxisSize: MainAxisSize.max,
                    children: [
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(6, 67, 0, 0),
                        child: ClipRRect(
                          borderRadius: BorderRadius.circular(8),
                          child: Image.asset(
                            'assets/images/MaisSaude2.png',
                            width: 70,
                            height: 70,
                            fit: BoxFit.cover,
                          ),
                        ),
                      ),
                      Padding(
                        padding: EdgeInsetsDirectional.fromSTEB(15, 70, 0, 0),
                        child: Container(
                          width: 274,
                          height: 28,
                          decoration: BoxDecoration(
                            color: Color(0xFF246536),
                            borderRadius: BorderRadius.only(
                              bottomLeft: Radius.circular(32),
                              bottomRight: Radius.circular(32),
                              topLeft: Radius.circular(32),
                              topRight: Radius.circular(32),
                            ),
                          ),
                          child: Text(
                            'Excluir dados Cadastrais',
                            textAlign: TextAlign.center,
                            style: FlutterFlowTheme.of(context)
                                .bodyMedium
                                .override(
                                  fontFamily: 'Rubik',
                                  color: Colors.white,
                                  fontSize: 21,
                                  letterSpacing: 0.0,
                                  fontWeight: FontWeight.w600,
                                ),
                          ),
                        ),
                      ),
                    ],
                  ),
                  Padding(
                    padding: EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                    child: Row(
                      mainAxisSize: MainAxisSize.max,
                      children: [
                        Flexible(
                          child: Align(
                            alignment: AlignmentDirectional(0, 0),
                            child: Column(
                              mainAxisSize: MainAxisSize.max,
                              children: [
                                Container(
                                  width: 280,
                                  height: 22,
                                  decoration: BoxDecoration(
                                    color: Color(0xFF153A71),
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(0),
                                      bottomRight: Radius.circular(0),
                                      topLeft: Radius.circular(15),
                                      topRight: Radius.circular(15),
                                    ),
                                  ),
                                ),
                                Align(
                                  alignment: AlignmentDirectional(0, 0),
                                  child: Container(
                                    width: 280,
                                    height: 101,
                                    decoration: BoxDecoration(
                                      color: FlutterFlowTheme.of(context)
                                          .secondaryBackground,
                                      borderRadius: BorderRadius.only(
                                        bottomLeft: Radius.circular(15),
                                        bottomRight: Radius.circular(15),
                                        topLeft: Radius.circular(0),
                                        topRight: Radius.circular(0),
                                      ),
                                    ),
                                    child: Align(
                                      alignment: AlignmentDirectional(0, 0),
                                      child: Text(
                                        'Dados Excluídos com Sucesso!',
                                        textAlign: TextAlign.center,
                                        style: FlutterFlowTheme.of(context)
                                            .bodyMedium
                                            .override(
                                              fontFamily: 'Rubik',
                                              color: Color(0xFF153A71),
                                              fontSize: 22,
                                              letterSpacing: 0.0,
                                              fontWeight: FontWeight.w600,
                                            ),
                                      ),
                                    ),
                                  ),
                                ),
                              ],
                            ),
                          ),
                        ),
                      ],
                    ),
                  ),
                  Align(
                    alignment: AlignmentDirectional(-1, -1),
                    child: Padding(
                      padding: EdgeInsetsDirectional.fromSTEB(20, 185, 0, 0),
                      child: Row(
                        mainAxisSize: MainAxisSize.max,
                        children: [
                          Flexible(
                            child: Align(
                              alignment: AlignmentDirectional(0, 0),
                              child: Padding(
                                padding:
                                    EdgeInsetsDirectional.fromSTEB(0, 30, 0, 0),
                                child: FFButtonWidget(
                                  onPressed: () async {
                                    context.pushNamed('SaudeLogin');
                                  },
                                  text: 'Sair',
                                  options: FFButtonOptions(
                                    width: 103,
                                    height: 22,
                                    padding: EdgeInsetsDirectional.fromSTEB(
                                        3, 0, 0, 0),
                                    iconPadding: EdgeInsetsDirectional.fromSTEB(
                                        0, 0, 0, 0),
                                    color: Color(0xFF246536),
                                    textStyle: FlutterFlowTheme.of(context)
                                        .titleSmall
                                        .override(
                                          fontFamily: 'Rubik',
                                          color: Colors.white,
                                          fontSize: 16,
                                          letterSpacing: 0.0,
                                        ),
                                    elevation: 0,
                                    borderRadius: BorderRadius.only(
                                      bottomLeft: Radius.circular(20),
                                      bottomRight: Radius.circular(20),
                                      topLeft: Radius.circular(20),
                                      topRight: Radius.circular(20),
                                    ),
                                  ),
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                    ),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}
