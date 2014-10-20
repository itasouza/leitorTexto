unit untLeitor;

interface

uses
  Windows, Messages, SysUtils, Variants, Classes, Graphics, Controls, Forms,
  Dialogs, ComCtrls, ExtCtrls, RLReport, RLRichText,  RLPDFFilter,
  RLHTMLFilter, RLFilters, RLRichFilter, RLPreviewForm, StdCtrls, Buttons;



type
  TfrmLeitor = class(TForm)
    Panel1: TPanel;
    PageControl1: TPageControl;
    tabFicha: TTabSheet;
    PanelFicha: TPanel;
    RLPreviewSetup1: TRLPreviewSetup;
    RLRichFilter1: TRLRichFilter;
    RLHTMLFilter1: TRLHTMLFilter;
    RLPDFFilter1: TRLPDFFilter;
    btnBuscaArquivo: TBitBtn;
    TabSheet1: TTabSheet;
    RLReport1: TRLReport;
    RLImage1: TRLImage;
    RLRichText1: TRLRichText;
    btnVisualizar: TBitBtn;
    Label1: TLabel;
    Label2: TLabel;
    editCaminho: TEdit;
    RLMemo1: TRLMemo;
    OpenDialog1: TOpenDialog;
    btnBuscarArquivo: TBitBtn;
    RichEditConteudo: TRichEdit;
    procedure btnVisualizarClick(Sender: TObject);
    procedure btnBuscaArquivoClick(Sender: TObject);
    procedure btnBuscarArquivoClick(Sender: TObject);
  private
    { Private declarations }
  public
    { Public declarations }
  end;

var
  frmLeitor: TfrmLeitor;

implementation


{$R *.dfm}

procedure TfrmLeitor.btnVisualizarClick(Sender: TObject);
begin
   RLReport1.Preview;
end;

procedure TfrmLeitor.btnBuscaArquivoClick(Sender: TObject);
var
   { Variável que recebe o conteúdo do arquivo texto }
   arquivo: TStringList;
   i: Integer;
begin

  //limpa tudo
  RichEditConteudo.Text := '';
 if FileExists(editCaminho.Text) then
  begin
         { Instancia a variável arquivo }
       arquivo := TStringList.Create;
    try
       { Carrega o conteúdo do arquivo texto para a   memória }
       arquivo.LoadFromFile(editCaminho.Text);
       { Realiza um loop em toda a lista }
    for i := 0 to arquivo.Count - 1 do   begin
      { Mostra o valor atual da linha }
       // ShowMessage('O conteúdo original da linha ' + IntToStr(i) + ' é ' + arquivo[i]);
        //escreve o conteudo dentro do rickedit
        RichEditConteudo.Lines.Add(arquivo[i]);
    end;
        { Salva as alterações no arquivo }
      //  arquivo.SaveToFile('c:\temp\arquivo1.txt');
    finally
       { Libera a instancia da lista da memória }
       RLMemo1.Lines.Add(RichEditConteudo.Lines.Text);
       FreeAndNil(arquivo);
     end;
  end;


end;

procedure TfrmLeitor.btnBuscarArquivoClick(Sender: TObject);
begin
 if OpenDialog1.Execute then
     editCaminho.Text := OpenDialog1.FileName;

end;

end.
